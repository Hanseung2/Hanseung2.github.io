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
###### Description
서울열린데이터광장에서 제공하는 JSON data와 OpenAPI를 이용한 지하철 통합 웹서비스로 지하철 각 역간 소요시간을 AI로 예측해 사용자에게 제공<br/>

1. 제공되는 역간 소요시간을 기본 가중치로 Dijkstra Algorithm을 수행해 최단 경로 3가지를 찾아 AI에게 넘겨줌. <br/>
2. 학습된 모델이 해당 경로에 대한 역간 소요시간을 반환 <br/>
3. 기존 3가지 경로의 총 소요시간과 예측된 총 소요시간을 비교하여 지연 시간 예측
<br/>

###### What I Do

✔ Dockerfile을 작성해 Flask(AI), Spring(BE), React(FE), MySQL(DB)을 각각 컨테이너화<br/>
✔ 각 서버를 Docker network를 통해 소통하게 하고, Docker compose를 이용해 컨테이너들을 한 번에 빌드하여 로컬 서버(8080 포트)에서 동작하도록 함<br/>
✔ 다양한 OpenAPI 호출과 React, Spring, Flask 간의 연동 (POST, fetch(), REST API) <br/>
✔ 지하철 역을 그래프로 만들어 Dijkstra Algorithm 을 이용한 출발지와 도착지 간의 경로 찾기 알고리즘 구현
<br/>

###### Review

프로젝트 고민 : [<span style="background-color:#fff5b1">https://hanseung2.github.io/capstone/subway1/</span>](https://hanseung2.github.io/capstone/subway1/)<br/>
프로젝트 중간 회고 : [<span style="background-color:#fff5b1">https://hanseung2.github.io/capstone/middlesubway/</span>](https://hanseung2.github.io/capstone/middlesubway/)

<hr/>
<br/>

## <center> Skills </center>
###### Backend
- Java
- Spring Boot
- Gradle
<br/>

###### DevOps
- Git
- Docker
- AWS EC2

<hr/>
<br/>

## <center> Blog </center>
깔끔하게 직접 블로그를 디자인 해보고 싶어 Jekyll를 이용해 Github blog를 만들어 개인 공부와 경험했던 트러블 슈팅들을 기록하고 있습니다. 매일 공부했던 내용을 기록하고 까먹지 않도록 노력하는 게 목표입니다.<br/>
[<span style="background-color:#fff5b1">https://hanseung2.github.io</span>](https://hanseung2.github.io/)