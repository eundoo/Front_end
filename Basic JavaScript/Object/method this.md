# 메서드와 'this'

객체는 사용자, 주문 등과 같이 실제 존재하는 개채를 표현하고자 할 때 생성된다.

## 메서드 만들기
---
```javascript
    let user = {
      name: 'John',
      age: 30
    };

    user.sayHi = function() {
      alert('whats up?')
    };

    user.sayHi();   //what's up?
```
위는 *함수 표현식*으로 함수를 만들고, 객체 프로퍼티에 함수를 할당해 주었다.
이렇게 객체 프로퍼티에 할당된 함수를 메서드 라고 부른다.
**위 예시에선 user에 할당된 sayHi가 메서드이다.**

```javascript
    let user = {
      name: 'Nana',
      age: 28
    };

    //함수선언문
    function sayHi() {
      alert('whats up?')
    };

    //선언된 함수를 메서드로 등록
    
    user.sayHi = sayHi;

    user.sayHi();   //what's up?
```

메서드는 위와 같이 이미 정의된 함수를 이용해서 만들 수도 있다.

## 메서드 단축 구문
---
```javascript
    user = {
      sayHi: function() {
        alert('whats up?')
      }
    };

    user = {
      sayHi() {   //sayHi: function()과 동일하다.
        alert('whats up?');
      }
    }
```

(funtion을 생략했네...)
위처럼 funtion을 생략해도 메서드를 정의할 수 있다.

## 메서드와 'this'
---
> this 값은 런타임에 결정된다. (내용에 따라 달라진다.) 

메서드 내부에서 this 키워드를 사용하면 객체에 접근 할 수 있다.

```javascript
    let user = {
      name: 'Nana',
      age: 28,

      sayHi() {
        alert(this.name);
      }
    };

    user.sayHi();   //Nana
```

### JS에서 허용되는 'this'

> this는 런타임에 결정되므로 메서드가 어디서 정의 되었는지에 관계없이 this는 점 앞의 객체가 무엇인가에 따라 자유롭게 결정된다. (값이 없는 객체에 this를 붙여도 *undefined*로 호출 할 수 있다.)

## this가 없는 화살표 함수
---
```javascript
    let user = {
      fisrtName: '나나',
      sayHi() {
        let arrow = () => alert(this.firstName);
        arrow();
      }
    };

    user.sayHi()    //나나
```

> 화살표함수는 this를 가지지 않으므로 화살표 함수에서 this를 참조하면 평범한 **외부 함수**에서 this 값을 가져온다.