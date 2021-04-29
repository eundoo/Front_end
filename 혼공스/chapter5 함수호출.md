API
---
Application Programming Interface(약속)
> 애플리케이션 프로그램을 만들때의 약속

```javascript
    alert('메세지')
    console.log('메세지')
```
이처럼 콘솔이 어떤방식으로 출력해주는지 몰라도 이 함수를 쓰면 출력해준다는 약속

나머지 매개변수
---
자료형이 무조건 배열이다.
```javascript
    const f = function(a,b,c,...매개변수입력) {
      const.log(a,b, 매개변수)
    }
    함수()          // []undefined
    함수(1)         // 1 undefined []
    함수(1,2)       // 1 2 []
    함수(1,2,3)     // 1 2 [3]
    함수(1,2,3,4)   // 1 2 [3,4]
```
- '...'에 남은 매개변수들이 들어온다.
- (매개변수, a, b) 처럼 앞에 올 수 없다.

전개연산자
---
'...'을 써서 함수를 호출해주는 특별한 문법이다. 배열에 있는 내용을 전개해서 실행할 수 있게 해준다.
```javascript
    const 함수 = function(a,b,c) {
      console.log(a,b,c)
    }

    const a = [1,2,3]
    함수(a[0], a[1], a[2])  //이렇게 일일이 넣어줘야하지만
    함수(...a)              //이렇게 하면 위와 똑같은 결과를 얻을 수 있다.
```