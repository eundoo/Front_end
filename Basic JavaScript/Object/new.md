# new 연산자와 생성자 함수

- 객체리터럴 { ... }을 사용해 객체를 쉽게 만들 수 있다.
- 유사한 객체를 여러 개 만들어야 할 때는 **new 연산자**와 생성자 함수를 사용해 만든다.

## 생성자 함수
---
1. 함수 이름의 첫 글자는 대문자로 시작한다.
2. 반드시 **new** 연산자를 붙여 실행한다.

```javascript
    function User(name) {
      this.name = name;
      this.isAdmin = false;
    }

    let user = new ser('Nana');

    alert(user.name);     //Nana
    alert(user.isAdmin);  //false  
```

## new.target과 생성자 함수
---
new.targer 프로퍼티를 사용하면 함수가 new와 함께 호출되었는지 아닌지를 알 수 있다.
일반적인 방법으로 함수를 호출했다면 new.targer은 undefined를 반환하고, new와 함께 호출한 경우엔 new.target은 함수 자체를 반환한다.

## 생성자와 return문
---
> 생성자 함수엔 보통 return문이 없다. 반환해야 할 것들은 모두 this에 저장되고, this는 자동으로 반환되기 때문에 반환문을 명시적으로 써 줄 필요가 없다.

그러나 return문이 있다면

- 객체를 return한다면, this 대신 객체가 반환된다.

```javascript
    function BigUser() {
      this.name = 'John';

      return {name: 'Nana'};    //this가 아닌 새로운 객체{}를 반환함
    }
    alert(new BigUser().name);    //Nana

- 원시형을 return한다면, return문이 무시된다.

    function SmallUser() {
      this.name = 'John';

      return;     //this를 반환함
    }
    alert(new SmallUser().name);  //John
```

## 생성자 내 메서드
---
```javascript
    function User(name) {
      this.name = name;

      this.sayHi = function() {
        alert('My name is : ' + this.name);
      };
    }

    let john = new User('John');

    john.sayHi();   //My name is: John

    /*
    john = {
      name: 'John',
      sayHi: function() { ... }
    }
    */
```

