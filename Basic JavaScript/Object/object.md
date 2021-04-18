# 객체

- 원시자료형
:하나의 데이터만 담을 수 있다. 
숫자형, BigInt, 문자형, 불린형, null값, undefined값,심볼

- 객체형
: 다양한 데이터를 담을 수 있다.
객체는 중괄호 {}를 이용해 만들 수 있다. 중괄호 안에는 **key:value** 쌍으로 구성된 프로퍼티를 여러개 넣을 수 있는데, *key에는 문자형*, 그리고 *value에는 모든 자료형*이 허용된다.

> 상수 객체는 수정될 수 있다.
```javascript
cont user  = {
  name: "Oh"
};

user.name = "Nana";

alert(user.name);   //Nana;
```

const는 user의 값을 고정하지만 그 내용은 고정하지 않는다.

## 대괄호 표기법

여러 단어를 조합해 프로퍼티 키를 만들 경우에는 점표기법을 사용해서 프로퍼티 값을 읽을 수 있지만, 공백이잇거나 숫자로 시작하거나 $,_ 를 제외한 다른 특수문자가 올 경우에는 문법 에러를 뱉어낸다.

이 경우 점 표기법 대신에 **대괄호 표기법**을 사용한다.

```javascript
    let user = {};

    //set
    user["likes birds"] = true;

    //get
    alert(user["likes birds"]);   //true

    //delete
    delete user["likes birds"];
```

    대괄호 표기법 안에서 문자열을 사용할 땐 문자열을 따옴표로 묶어줘야 한다.

다른 예시

```javascript
    let user = {
      name: "nana",
      age: 28
    };

    let key = prompt("사용자의 어떤정보를 얻고싶으세요?" , "name");

    alert(user[key]);   //nana

그러나 점 표기법은 이런 방식이 불가하다.

    let user = {
      name: "nana",
      age: 28
    };

    let key = "name";
    alert(user.key)   //undefined

## 계산된 프로퍼티
---

객체를 만들 때 리터럴 안에 프로퍼티 키가 대괄호로 둘러싸여 있는 경우, 이를 계산된 프로퍼티라고 부른다.

    let fruit = prompt("어떤 과일을 구매하시겠습니까?", "apple");

    let bag = {
      [fruit]: 5,   //변수 fruit에서 프로퍼티 이름을 동적으로 받아온다.
    };

    alert (bag.apple);    //fruit에 "apple"이 할당되었다면, 5가 출력된다.

    ----------------------------------------------------------------------

    let fruit = prompt("어떤 과일을 구매하시겠습니까?", "apple");
    let bag = {};

    bag[fruit] = 5;

## 단축 프로퍼티
---
실무에선 프로퍼티 값을 기존 변수에서 받아와 사용하는 경우가 종종있다.

    funtion makeUser(name, age) {
      return {
        name,   //name: name과 같음
        age     //age: age와 같음
      };
    }

    let user = makeUser("nana", 28);
    alert(user.name);   //nana
```

### 프로퍼티 이름의 제약사항

객체 프로퍼티에는 for / let / return ... 등 예약어를 키로 사용해도 무방하다.

## in 연산자로 프로퍼티 존재 여부 확인하기
---
자바스크립트는 객체의 중요한 특징 중 하나로 다른언어와 달리, 존재하지 않는 프로퍼티에 접근하려 해도 에러가 발생하지 않고 'undefined'를 반환한다.

> 'key' in object   //'key' 부분에 찾는 key를 넣는다.

```javascript
    let user = {neme: 'nana', age:28};

    alert('age' in user);       //true
    alert('blabla' in user);    //false
```

== undefined와 in 의 작은 차이로는
키와 값이 *test: undefiend* 라고 할때 == undefined를 사용하면 undefined으로 출력되는데 실제로는 값이 있지만 혼란을 줄 수 있다.
그러나 in을 사용하면 프로퍼티 유무를 제대로 확인 할 수 있다.

## for in 반복문
---
for in 반복문을 사용하면 객체의 모든 키를 순화할 수 있다.
for in 반복문은 for( ; ; ) 반복문과는 완전히 다르다.

```javascript
    문법은 이렇다.
    for (key in object){

    }

    --------------------------------------------------------------------
    let user = {
      name: "Nana",
      age: 28,
      isAdmin: true
    };

    for (let key in user) {
      //키
      alert(key);          //name, age, isAdmin
      //키에 해당하는 값
      alert(user[key]);    //Jone, 30, true 
    }
    요렇게 실행하면 객체 user의 모든 프로퍼티가 출력된다.
```

for in 반복문에도 for( ; ; )문처럼 반복 변수를 선언 (let key) 했다는 점에 주목..!

반복변수명은 자유롭게 정할 수 있다. 'for (let prop in obj)' 같이 key 말고 다른 변수명을 사용해도 괜찮다.



