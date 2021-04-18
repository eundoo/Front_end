# 프론트엔드의 상태관리

### 상태(State) 

화면구성에 필요한 데이터를 상태라고 부른다.

> ex) 인스타그램 
  내가 올린 사진들
  게시물 수
  팔로워 수 
  새로운 알림
  내가 현재 로그인 되어 있는지 여부...등

### 상태관리

데이터에 맞춰 적절하게 UX/UI를 설계하고 구현하는것
ex) 글자,이미지...등 늘어나고 줄어듦에 따라 ('동적으로 변하는것들을') 가독성이 좋게 변화시킨다. (235,000팔로워 -> 235k)

## UX/UI???
---
UX(User Experience)디자인은 사용자 경험을 의미한다. 사용자가 어떤 제품, 시스템, 서비스 등을 직,간접적으로 이용한 후 느낀 반응이나 행동과 같은 경험들을 총체적으로
설계하는 것이 UX디자인이다.

UI(User Interface)디자인은 사용자가 제품을 어떤 방식으로 이용하도록 만드느냐는 디자인하는 것. 즉 겉으로 시각화 되는 작업. 사용자가 실제로 마주하게 될 
디자인, 레이아웃 등을 아우르는 개념.

ex) 배민 어플 (오늘날X 수정 전)
위에 치킨,피자,중식 등등 메뉴가 먼저 눈에 띄게 나와있어서 소비자들이 먼저 그 메뉴들을 고려하고, 원하는게 없다 혹은 뭔가 서칭을 원한다 했을때 페이지를 아래로 내려 
검색창에서 검색을 하게 만든다. -> UI

그러나 배가고파 음식을 빨리 배달시켜 먹고 싶은 소비자들은 다양한 카테고리를 일일이 검색하기 보다 자신이 먹고싶은 주변 음식점들을 재빠르게 확인하고 싶을 것이고
그래서 검색창이 어디 있나 찾을 때, 맨 첫페이지 위에 위치해 있는 검색엔진들과 다르게 밑으로 내려야만 검색창을 찾을 수 있는 이 어플에 디자인이 경험적으로 
불편하다고 느낄것. -> UX

## ReactJS 상태관리
---
(아직은 이해하기 어려움..... /일단 블로그펌)
React로 application 만들 때 필수적으로 상태를 관리하는 상황을 마주치는데 기본적으로 state에 기본 값을 지정하고 setState를 사용하여 data를 추가,제거 그리고 수정한다. 
독립적인 component내에서 뿐만 아니라 부모-자식, 부모-자식-자식의 자식- 자식의 자식의 자식, 혹은 그 역순과 사돈/팔촌 관계끼리도 state를 공유하고 수정하고 다시 공유할 수 있다.
state를 props로 서로 넘겨주며 data를 공유하고 setState를 통해 data를 수정하는 등 간단한 방법으로 React에서 상태 관리를 할 수 있지만 
application의 규모가 복잡해지고 커질수록 상태 관리는 더욱 더 힘들어진다.무엇이 이 간단한 방법을 복잡하고 어렵게 만드는지 알아보기 위해선 
우선 React의 특성을 알아볼 필요가있다.

## Redux
---
리덕스는 상태관리 라이브러리이다. 리덕스를 사용하면 애플리케이션의 전체상태를 관리 할 수 있다. 

> 리덕스를 사용했을 때의 장점
  1. 컴포넌트 코드로 부터 상태관리 코드를 분리할 수 있다.
  2. 미들웨어를 활용한 다양한 기능을 추가할 수 있다.
  - 강력한 미들웨어 라이브러리
  - 로컬 스토리지에 데이터 저장하기 및 불러오기
  3. SSR(Server Side Rendering)시에 데이터 전달이 간편하다.
  4. 리액트 컨텍스트보다 효율적인 렌더링이 가능하다.

리덕스를 사용하면 컴포넌트 코드로부터 상태관리 코드를 분리할 수 있다. 아무래도 컴포넌트에서 상당히 많은 코드를 작성하게 되는데, 그러다 보면 컴포넌트 코드가 많아져서 
가독성이 떨어진다. 그러므로 상태관리 코드를 분리해주면 컴포넌트 코드가 좀 더 가벼워 진다.
예를 들어 루트 컴포넌트 밑에 만 개의 하위 컴포넌트가 있다고 할 때, 이 중 루트 컴포넌트에 영향을 줄 수 있는 하나의 값이 바뀌었는데 
그 값을 루트 컴포넌트를 통해 다른 컴포넌트도 사용하고 있다면 기존 패턴에서는 이러한 변경 내용에 일일히 대응하는 코드를 작성하기가 어렵다.