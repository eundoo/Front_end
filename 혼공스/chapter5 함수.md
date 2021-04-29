윤년 구하기 연습
---
- 4로 나누어 떨어지는 해는 윤년이다.
- 하지만 100으로 나누어 떨어지는 해는 윤년이 아니다.
- 하지만 400으로 나누어 떨어지는 해는 윤년이다.

함수 선언문보다 , 함수 표현식이 더 선호된다.

```javascript
    const isLeapYear = funcion (연도) {
      const 윤년이면 = 
        (연도 % 4 === 0)          //윤년
        && (연도 % 100 !== 0)     //윤년
        || (연도 % 400 ===0)      //윤년

        if(윤년이면) {
          return true
        } else {
          return false
        }
}
    이렇게 아래로 쓰면 가독성도 좋고 짧다.
    const isLeapYear = function(연도) {
      return (연도 % 4 ===0)
        && (연도 % 100 !== 0)
        || (연도 % 400 === 0)
    }

    console.log(`2020년은 윤년일까? === ${isLeapYear(2020)}`) //윤년 -> true
    console.log(`2010년은 윤년일까? === ${isLeapYear(2010)}`) //윤년X -> false
    console.log(`2000년은 윤년일까? === ${isLeapYear(2000)}`) //윤년 -> true
    console.log(`1900년은 윤년일까? === ${isLeapYear(1900)}`) //윤년X -> false
```
