# 옵셔널 체이닝 '?.'

프로퍼티가(문자열이 가지고 있는 고유의 정보) 없는 중접 객체를 에러 없이 안전하게 접근할 수 있다.

## 옵셔널 체이닝이 필요한 이유
---
- 사례1
사용자가 여러명 있는데 그 중 몇명은 주소 정보를 가지고 있지 않다. 이럴 때 user.address.street를 사용해 주소 정보에 접근하면 에러가 발생할 수 있다.

```javascript
    let user = {};  //주소가 없는 사용자

    alert(user.address.street);   //TypeError: Cannot read property 'street' of undefiend
```

- 사례2
브라우저에서 동작하는 코드를 개발할 때 발생할 수 있는 문제로 페이지에 존재하지 않는 요소에 접근해 요소의 정보를 가져오려 할 때 발생.

```javascript
    //querySeletor(...) 호출 결과가 null인 경우 에러 발생
    let html = document.querySelector('.my-element').innerHTML;

    //명세서에 ?가 추가되기 전에는 이런 문제들을 해결하기 위해 && 연산자를 사용했다.
    let user = {};    //주소가 없는 사용자
    
    alert(user && user.address && user.address.street);   //undefined에러가 발생하지 않음 그러나 코드가 아주 길어짐
```

## 옵셔널 체이닝 등장
---
?.은 ?.앞 평가대상이 undefined나 null이면 평가를 멈추고 undefined를 반환한다.

```javascript
    let user = {};    주소 정보가 없는 사용자

    alert(user?.address?.street);   
    //undefined가 출력되고 에러가 발생하지 않음, 옵셔널 체이닝을 이용해 안전하게 접근
```

user?.address를 주소로 읽으면 아래와 같이 user객체가 존재하지 않더라도 에러가 발생하지 않음

```javascript
    let user = null;

    alert(user?.address);         //undefined
    alert(user?.address.street);  //undefiend
```

- ?.은 ?.'앞'평가 대상에만 동작되고, 확장은 되지 않는다.
- ?.앞의 변수는 꼭 선언되어 있어야 한다.

## 단락평가
---
> ?.는 왼쪽 평가대상에 값이 없으면 즉시 평가를 멈춘다.

## ?.() 와 ?.[]
---
> ?.는 **연산자가 아니다**

1. obj?.prop – obj가 존재하면 obj.prop을 반환하고, 그렇지 않으면 undefined를 반환함
2. obj?.[prop] – obj가 존재하면 obj[prop]을 반환하고, 그렇지 않으면 undefined를 반환함
3. obj?.method() – obj가 존재하면 obj.method()를 호출하고, 그렇지 않으면 undefined를 반환함