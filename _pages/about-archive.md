---
permalink: /about/
layout : single
title : About
---


<br/>


## <center> Profile </center>


<center>Sejong univ. - Department of Computer Engineering (2019.03 ~ )</center>
<br/><br/>
<hr/>

<br/>

## <center> Project </center>

#### 1️⃣ 서울시 실시간 지하철 예측 서비스(Web) <span style="display:inline-block; margin-left:10px;">
[🔔Poster link](/assets/images/20240627/Capstone.jpg)
</span>

서울열린데이터광장에서 제공하는 JSON data와 OpenAPI를 이용한 지하철 통합 웹서비스로 지하철 각 역간 소요시간을 AI로 예측해 사용자에게 제공<br/>

> 1. 제공되는 역간 소요시간을 기본 가중치로 Dijkstra Algorithm을 수행해 최단 경로 3가지를 찾아 AI에게 넘겨줌. <br/>
2. AI가 해당 경로에 대한 소요시간을 분석하여 반환 <br/>
3. 기존 3가지 경로의 총 소요시간과 예측된 총 소요시간을 비교하여 지연 시간 예측
<br/>

✔ Dockerfile을 작성해 Flask(AI), Spring(BE), React(FE), MySQL(DB)을 각각 컨테이너화<br/>
✔ 각 서버를 Docker network를 통해 소통하게 하고, Docker compose를 이용해 컨테이너들을 한 번에 빌드하여 로컬 서버(8080 포트)에서 동작하도록 함<br/>
✔ 다양한 OpenAPI 호출과 React, Spring, Flask 간의 연동 (POST, fetch(), REST API) <br/>
✔ 지하철 역을 그래프로 만들어 Dijkstra Algorithm 을 이용한 출발지와 도착지 간의 경로 찾기 알고리즘 구현
<br/>

### ✅프로젝트 후기

프로젝트 고민 : [<span style="background-color:#fff5b1">https://hanseung2.github.io/capstone/subway1/</span>](https://hanseung2.github.io/capstone/subway1/)


<br/><br/>

# <center> Tech Stack </center>

### <center>Familiar</center>

<center>C, C#, Python, Unix, HTML, CSS</center>

<br/>

### <center>Studying</center>

<center>Spring, Java, Git</center>