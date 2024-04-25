---
layout: single
title:  "[Capstone] [실시간 지하철 지연 예측 서비스] 2. 중간 발표 후 회고"
categories: Capstone





---



4학년 1학기 Capstone디자인(산학협력프로젝트)에 대한 고민과 방향성
{: .notice--danger}



### 현 진행 상황

1️⃣ 프로젝트 구조

![](/assets/images/20240421/TSA.png)

처음 프로젝트 기술 정하는 것도 막막했고 어디서 부터 시작해야 하나 걱정도 많았지만, 나름 잘 짜여진 구조처럼 보여 뿌듯하다.

<br/>

### 해결 했던 오류들

기본적으로 React와 서버간의 연동에 오류를 해결했다. 

#### 1️⃣ 8080 포트(Backend)에서 Kakao Map API 오류

Spring 개발시 React와 연동해 잘 적용하는지 보려고 Spring의 build.gradle에 React의 index.html 등 정적파일을 Spring으로 복사해 서빙할 수 있게 해 Spring Application만 실행시켜도 http://localhost:8080 에서 동시에 볼 수 있도록 구성했지만, 우리의 메인 소스인 Kakao Map이 불러와지지 않았다.

Chrome 브라우저 검사의 Network 오류를 보니 CORB 오류라고 나왔고, 이 오류 때문에 한 3일 정도 코드를 고쳤던 거 같다. Nginx를 추가 해보기도 하고 PostMapping을 이용해 Spring에서 불러와보기도 하고 docker network를 구성해보기도 하고 CORS 헤더를 전송하기도 했지만 전혀 해결되지 않았다.

그러다 구글에서 나와 같이 Kakao API에서 CORS 오류를 해결하신 분이 계셨다.

해결법은 너무 간단했다.. Kakao Develop 사이트에서 API 등록할때 허용 도메인에 localhost:8080을 넣어주면 됐다. React에서 3000번을 쓰는데 연동하려고 8080에서 여니 권한이 없어 지도 API가 열리지 않는 것이었다.

허탈하긴 했지만, CORS 오류가 악명 높은 이유를 조금이나마 느꼈고 많이 배웠다.



#### 2️⃣ Flask(AI Model)와 React(Frontend) 사이의 통신

아직 인공지능 모델을 구축하진 않았지만, 실시간 정보와 함께 지연 예측된 정보도 같이 받아오면 될 거 같아 일단 Flask 쪽에서 공공데이터 api를 호출하게 했다. 그래서 이것을 스프링 컨트롤러를 통해 데이터를 가져와 react로 전달하려고 했는데, 그럼 2번 거치게 되니 상대적으로 클라이언트에게 제공하는 시간도 오래 걸릴 것이라고 판단해 react와 flask 사이에서만 주고 받을 수 있게 했다.

첫번째 에러는 2개의 터미널 창에서 각각의 서버를 실행시에는 정보를 전달받던게 Docker-compose 이용시 전달받지 못하던 상황이다. `npm start` 로 react 서버를 열고, `app.py`을 실행해 flask 서버를 열어 `axios`함수를 이용해 /receive_subway 엔드 포인트로 GET 요청시 해당 공공데이터 api의 json 파일을 잘 받아오는지 확인해봤더니 잘 통신이 되었다. 하지만, Docker compose를 이용하니 컨테이너 사이의 통신이 안 됐다. 

👉 해결 : Docker network를 이용해 서비스들을 하나의 네트워크로 연결해 통신하게 했고 react에서 요청하는 url 을 `localhost:8082` 에서 `flask:8082` 로 바꿔주니 해결되었다. 컨테이너 사이의 통신에는 Docker network 지정이 필요하다고 느꼈다!

<br/>

두번째 에러는 GET, POST 요청은 서버로 들어가지만, 웹 브라우저의 검사를 통해 Header를 보니 'application/json' 415 에러와 data에 staionName이 제대로 들어가지 않던 것이다.

React의 Kakao Map의 특정 지하철역의 마커를 클릭해 `실시간 도착 정보` 버튼을 누르면 해당 StaionName 을 Flask로 전달해 맞는 공공데이터 api의 json데이터를 실시간으로 호출하는 방식을 택했다. 하지만, Flask로 POST요청은 가는데 stationName을 제대로 전달해주지 않았다.

👉 먼저, 구글링에서 찾은 정보인 헤더에 "Content-Type": "application/json" 을 추가하여 전달해주었다. 그래도 되지 않아 처음부터 끝까지 코드를 의심해보았다.

결론은, 데이터 형식의 문제였다. `app.py` 에서 공공데이터 api를 호출할때 `기본 url + 해당 역이름`으로 호출해 해당 역 이름을 문자열로 받아야하는데 그냥 무작정 AI 파트를 맡은 형에게 코드를 받아 실행하다보니 이 사실을 놓쳤다. 

```python
data = request.json
station_name = data.get('stationName')
```

그래서 이런식으로 json 데이터를 받아 stationName 키에 해당하는 value를 저장해 url을 만들었고 React 에서는 

```jsx
 const response = await fetch("http://flask:8082/receive_subway_arrive", {
                method: "POST",
                headers: {
                    "Content-Type": "application/json",
                },
                body: JSON.stringify({ "stationName": stationName }),
            });
            const data = await response.json();
}
```

이렇게 fetch를 이용해 staionName을 JSON 형식으로 바꿔 Flask에 전달하게 했다.

이러니 실시간 도착 정보를 잘 불러올 수 있었다.

> 처음에는 React에서 axios 함수를 이용해 전달했는데 계속 오류가 나서 fetch를 이용해 해보았다. 차이점은 기회가 있으면 공부해봐야겠다.



### 불편했던 점

실전에서는 어떻게 되는지 알 수 없지만, 프로젝트 백엔드 파트를 맡았더니 프론트 코드도 건드려야하고 인공지능 모델쪽 코드도 건드려야했다. 조금이나마 코드를 공부하면서 React와 Flask가 어떻게 돌아가는지 알 수 있어 좋았지만 한편으로는 뭔가 체계화되어 있지 않는 코드를 던져주면 내가 연결시켜야 하는 느낌이 있었다. 

또한, 한번에 연결시켜 빌드하고 싶을때는 Docker-compose를 이용하여 실행시켰는데 코드를 수정하고 npm run build -> ./gradlew build -x check -> docker compose up --build 의 세 단계가 너무 시간이 오래 걸렸다. 



