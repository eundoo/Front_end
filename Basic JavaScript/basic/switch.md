# Switch문

## 복수의 if조건문은 switch문으로 바꿀 수 있다.
---
```javascript
    let a = 2 + 2;

    switch (a) {
      case 3:
        alert('비교하려는 값보다 작습니다.');
        break;
      case 4:
        alert('비교하려는 값과 일치합니다.');
        break;
      case 5:
        alert('비교하려는 값보다 큽니다.')
        break;
      default:
        alert('어떤 값인지 파악할 수 없습니다.')
    }
```

> break가 없으면 break문을 만날 때 까지 case4 아래의 코드들이 실행된다. (조건에 부합하는지 
아닌지 확인하지 않고)
> swtich문과 case문은 모든 형태의 표현식을 인수로 받는다.

## 여러개의 'case'문 묶기
---
코드가 같은 case문은 한데 묶을 수 있다.

```javascript
    case 3:
      alert('계산이 틀립니다.');
      alert('수학을 다시 공부하세요');
      break;
    case 5:
      alert('계산이 틀립니다.');
      alert('수학을 다시 공부하세요');
      break;

    위 코드를 

    case 3:
    case 5:
      alert('계산이 틀립니다.');
      alert('수학을 다시 공부하세요');
      break;

    이렇게 바꿀 수 있다.
```

## 자료형의 중요성
---
**비교하려는 값의 자료형이 같아야 한다.**

```javascript
    let arg = prompt('값을 입력하세요');    //prompt함수는 문자열을 반환하기 때문에 '0'으로 입력된다.
    
    switch (arg) {
      case '0':
        alert('0을 입력하셨습니다.')
        break;
      case 0:
        alert(이것은 실행되지 않습니다.)
        break;
    }

    위 두개는 비교하려는 자료형이 다르다.
```

