# 숫자형

1. 일반적인 숫자
2. 임의의 길이를 가진 정수 bigInt(2의 53승 이상이거나 -2의53승 이하의 제약 적용 X) 숫자로 나타낼 수 있다. 

## 진수 / toString(base) / 어림수 구하기 홈페이지 자료참조
---
## 부정확한 계산
---
숫자가 너무 커지면 64비트 공간이 넘쳐서 Infinity로 처리된다.

> toFixed(n)으로 해결 할 수 있지만 항상 문자열로 반환한다.

## isNaN과 isFinite
---
- Infinity와 -Infinity 그 어떤 숫자보다 큰 혹은 작은 특수 숫자 값
- NaN 에러를 나타내는 값

- isNaN(value)는 인수를 숫자로 변환한 다음 NaN인지 테스트함

```javascript
    alert(isNaN(NaN));    //true
    alert(isNaN("str"));  //true
```

- isFinite(value) – 인수를 숫자로 변환하고 변환한 숫자가 NaN/Infinity/-Infinity가 아닌 일반 숫자인 경우 true를 반환함

```javascript
    alert( isFinite("15") ); // true
    alert( isFinite("str") ); // false, NaN이기 때문
    alert( isFinite(Infinity) ); // false, Infinity이기 때문
```

## parselnt(정수)와 parseFloat(부동소수점 숫자)
---
단항 덧셈 연산자 + 또는 Number()를 사용하여 숫자형으로 변형할 때 피연산자가 숫자가 아니면 형 변환이 실패된다.

두 함수는 불가능할 때까지 문자열에서 숫자를 '읽는다'. 숫자를 읽는 도중 오류가 발생하면 이미 수집된 숫자를 반환한다.

```javascript
    alert( parseInt('100px') ); // 100
    alert( parseFloat('12.5em') ); // 12.5

    alert( parseInt('12.3') ); // 12, 정수 부분만 반환
    alert( parseFloat('12.3.4') ); // 12.3, 두 번째 점에서 숫자 읽기를 멈춥
```

## 기타 수학 함수
---
> Math.random() //0과 1사이의 난수 반환

> Math.max() //인수 중 최대/최소값을 반환

> Math.pow() //n을 power번 거듭제곱한 값 반환
