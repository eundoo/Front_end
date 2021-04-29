# 자료형

기본자료형 <Number, BigInt, String, Boolean, Null, Undefined, Symbol, Object>

자바스크립트의 변수는 자료형에 관계없이 모든 데이터 일 수 있다. 따라서 변수는 어떤 순간에 문자열일 수 있고 숫자일 수도 있다.

> 예를 들어 자바는 int 정수형, String 문자열, char 문자형... 등 으로 나뉘는데 자바스크립트는 값이 문자였다가 숫자로 바뀔 수도 있고, 반대의 경우나 다른 경우도 가능하다.

```javascript
let tnx = 'thank you';
tnx = 486;
```

## 숫자형 & BigInt
---
일반적인 숫자 외에
- **(1/0)  또는 (Infinity)** 로 무한대를 나타낼 수 있다.
- NaN = Nat a Number (계산중에 에러가 발생했다는 것을 나타내주는 **값** 예를들어 숫자가 아닌것과 숫자랑 연산했을때....)

## BigInt
---
정해진 값보다 큰 값 혹은 작은 정수는 숫자형을 사용해 나타낼 수 없는데 정수 리터럴 끝에 n을 붙이면 그 보다 적거나 큰 값을 사용할 수 있다. 

## 문자형
---
 ' ' 와 " " 의 차이를 두지 않는다.
 
```javascript
alert(`문자 ${ }`); 		//이렇게 백틱을 사용할 수 있다.
``` 

### typeof

- null 의 type of는 object이다. (객체가 아니다)
- typeof는 피연산자가 함수이면 function을 반환한다.