---
permalink: /about/
layout : single
title : About
---


<br/>

## <center> Profile </center>


- Sejong univ. Department of Computer Engineering (2019.03 ~ )
- Capstone디자인(산학협력프로젝트) (2024.03 ~ 2024.06)
- 힛더북 App 프로젝트 (2024.07 ~ )
- (주)블루솔루션즈 현장실습 (2024.09 ~)

<br/>
<hr/>
<br/>

## <center> Blog </center>
깔끔하게 직접 블로그를 디자인 해보고 싶어 Jekyll Themes를 이용해 Github blog를 만들어 개인 공부와 경험했던 트러블 슈팅들을 기록하고 있습니다. 공부했던 내용을 기록하고 까먹지 않도록 노력하는 게 목표입니다.<br/>

<br/>
<hr/>
<br>

## <center> Skills </center>
###### Backend
- ERD 설계와 Swagger를 통한 API 문서화가 가능합니다.
- Spring MVC 패턴을 기반으로 한 RESTful API 설계가 가능합니다.
- JPA를 활용해 리포지토리 계층을 구축하고, 효율적으로 데이터에 접근할 수 있습니다.
<br/>

###### DevOps
- Git을 통한 버전 관리가 가능합니다.
- Spring Boot, React, Flask, MySQL등을 Docker와 Docker Compose로 관리할 수 있습니다.
- AWS EC2 서버를 PuTTY를 이용해 사용할 수 있습니다.
<br/>

###### etc
- 상대를 배려하면서 말하고자 하지만, 내 생각과 다를 땐 확실히 표현하고자 합니다.
- 팀원들과 문제를 같이 해결하고 성장하고자 합니다.
- 오류가 발생하면 끝까지 해결하려고 합니다.

<br/>
<hr/>
<br/>

## <center> Project </center>

[<span style="background-color:#fff5b1">🔔Poster link</span>](/assets/images/20240627/Capstone.jpg)
#### 서울시 실시간 지하철 예측 서비스(Web) 
###### Description
서울열린데이터광장에서 제공하는 JSON data와 OpenAPI를 이용한 지하철 통합 웹서비스로 각 지하철역에 대한 정보들을 제공하고, 서울교통공사가 제공하는 역간 소요시간으로 경로찾기를 진행함과 동시에 AI로 예측해 사용자에게 제공한다.

###### What did I do

✔ Dockerfile로 Flask(AI), Spring(BE), React(FE), MySQL(DB)을 각각 컨테이너화<br/>
✔ 각 서버를 Docker network와 Docker compose로 관리<br/>
✔ 다양한 OpenAPI 호출과 React, Spring, Flask 간의 연동<br/>
✔ 지하철 역들을 그래프로 만들어 Dijkstra Algorithm 을 이용한 출발지와 도착지 간의 경로 찾기 서비스 구현
<br/>

###### Review

[<span style="background-color:#fff5b1">Capstone 회고</span>](https://hanseung2.github.io/categories/#capstone)

<br/>
<hr/>

#### 힛더북(App) 

###### Description
플래너, 타이머, 미션 기능이 있는 스터디 앱으로서 레벨을 올리고 엠블럼을 수집하며 재밌게 공부를 할 수 있게 한다.

###### What did I do

✔ 도메인형 패키지 구조를 선택, 각 도메인별 MVC 패턴을 기반으로 한 RESTful API 설계 및 개발<br/>
✔ 엔티티(Entity), 서비스(Service), 컨트롤러(Controller), DTO를 설계하고 서비스 코드의 부담을 줄이기 위해 Helper를 두어 중요하지 않은 비즈니스 로직을 처리하도록 함<br/>
✔ Swagger를 통한 API 문서화<br/>
✔ Spring Data JPA를 사용한 CRUD 기능 개발 및 데이터베이스 관리<br/>