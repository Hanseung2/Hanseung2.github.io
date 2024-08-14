---
layout: single
title:  "[힛더북] 3. Convention 정리"
categories: "AppProject"
sidebar_main: true
---

프로젝트에서 정한 컨벤션에 대해 정리
{: .notice--danger}



### Method Naming Convention

#### Camel Case 사용

- 메서드 이름은 소문자로 시작하고, 각 단어의 첫 글자는 대문자로 표기(Camel Case)



#### get vs find

- get -> return type이 T인 경우
- find -> return type이 Optional<T>인 경우



#### get 남발하지 않기

get은 객체가 가지고 있는 필드값을 그대로 가져올 때만 사용한다. 추가적인 연산을 하고 가져온다면 get이 아닌 적절한 변수명을 짓도록 하자.



#### Lombok getter setter 지양하기

getter는 캡슐화를 저해하고 (private로 숨겨둔 필드가 모두 드러난다.) 

setter는 객체를 불변하지 않게 한다.



#### 행동에 따라

- 속성에 접근: get/set
- 데이터 생성: create
- 데이터 조회: find
- 데이터 변경: modify
- 데이터 삭제: delete
- 데이터 입력: input
- 데이터 초기화: init
- 데이터 불러오기: load
- 데이터 유무 확인: has
- B를 기준으로 A를 하겠다: By



#### 접미사 vs 접두사

- Controller
  - 내용 + 접근/생성/조회 등등 : 접두사로 내용인 나옴
- Service
  - 접근/생성/조회 등등 + 내용 : 접미사로 내용이 나옴

<br/>

<hr/>

### Github Commit Convention

- feature : 새로운 기능 추가
- fix : 버그 수정
- docs : 문서 수정
- style : 코드 포맷팅, 세미콜론 누락, 코드 변경이 없는 경우
- refactor : 코드 리팩토링
- test : 테스트 코드, 리팩토링 테스트 코드 추가
- chore : 빌드 업무 수정, 패키지 매니저 수정 등 (code와 무관한 부분)
- comment : 주석 추가 및 변경
- remove : 파일, 폴더 삭제
- rename : 파일, 폴더명 수정

