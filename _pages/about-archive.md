---
permalink: /about/
layout : single
title : About
---


<br/>


## <center> Profile </center>


<center>- Sejong univ. Department of Computer Engineering (2019.03 ~ )</center>
<center>- Capstone디자인(산학협력프로젝트) (2024.03 ~ 2024.06)</center>
<br/><br/>
<hr/>

<br/>

## <center> Project </center>

[<span style="background-color:#fff5b1">🔔Poster link</span>](/assets/images/20240627/Capstone.jpg)
#### 서울시 실시간 지하철 예측 서비스(Web) 
![](/assets/images/route.jpg)
###### Description
서울열린데이터광장에서 제공하는 JSON data와 OpenAPI를 이용한 지하철 통합 웹서비스로 지하철 각 역간 소요시간을 AI로 예측해 사용자에게 제공<br/>

1. 제공되는 역간 소요시간을 기본 가중치로 Dijkstra Algorithm을 수행해 최단 경로 3가지를 찾아 AI에게 넘겨줌. <br/>
2. 학습된 모델이 해당 경로에 대한 역간 소요시간을 반환 <br/>
3. 기존 3가지 경로의 총 소요시간과 예측된 총 소요시간을 비교하여 지연 시간 예측
<br/>

###### What did I do

✔ Dockerfile을 작성해 Flask(AI), Spring(BE), React(FE), MySQL(DB)을 각각 컨테이너화<br/>
✔ 각 서버를 Docker network를 통해 소통하게 하고, Docker compose를 이용해 컨테이너들을 한 번에 빌드하여 로컬 서버(8080 포트)에서 동작하도록 함<br/>
✔ 다양한 OpenAPI 호출과 React, Spring, Flask 간의 연동 (POST, fetch(), REST API) <br/>
✔ 지하철 역을 그래프로 만들어 Dijkstra Algorithm 을 이용한 출발지와 도착지 간의 경로 찾기 알고리즘 구현
<br/>

###### Review

프로젝트 고민 : [<span style="background-color:#fff5b1">https://hanseung2.github.io/capstone/subway1/</span>](https://hanseung2.github.io/capstone/subway1/)<br/>
프로젝트 중간 회고 : [<span style="background-color:#fff5b1">https://hanseung2.github.io/capstone/middlesubway/</span>](https://hanseung2.github.io/capstone/middlesubway/)<br/>
프로젝트 마무리 회고 : [<span style="background-color:#fff5b1">https://hanseung2.github.io/capstone/final/</span>](https://hanseung2.github.io/capstone/final/)

<hr/>
<br/>

## <center> Skills </center>
###### Backend
- Spring Boot(Java)를 이용한 프로젝트 경험이 있습니다.
- Controller의 PostMapping을 통해 React와 Flask를 연동할 수 있고 객체를 서비스 결과물로 반환하여 사용자에게 제공할 수 있습니다.
- Gradle Wrapper를 이용해 빌드할 수 있습니다.
<br/>

###### DevOps
- Git을 통한 버전 관리가 가능합니다.
- Spring Boot, React, Flask, MySQL 의 Dockerfile 작성과 docker-compose.yml을 작성할 수 있습니다.
- AWS EC2 서버를 PuTTY로 접속하고 이용할 수 있습니다.
<br/>

###### etc
- 상대를 배려하면서 말하고자 하지만, 내 생각과 다를 땐 확실히 표현하고자 합니다.
- 팀원들과 문제를 같이 해결하고 성장하고자 합니다.
- 오류가 발생하면 끝까지 해결하려고 합니다.

<hr/>
<br/>

## <center> Blog </center>
깔끔하게 직접 블로그를 디자인 해보고 싶어 Jekyll를 이용해 Github blog를 만들어 개인 공부와 경험했던 트러블 슈팅들을 기록하고 있습니다. 공부했던 내용을 기록하고 까먹지 않도록 노력하는 게 목표입니다.<br/>
[<span style="background-color:#fff5b1">https://hanseung2.github.io</span>](https://hanseung2.github.io/)