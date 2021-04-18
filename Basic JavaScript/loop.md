## while
---
```javascript
    let i = 0;
      while(condition) {  //0, 1, 2가 출력
        alert(i);
        i++;
      }
```

## for
---
```javascript
    인라인 변수 선언
      for (let i = 0; i < 3; i++> {
        alert(i);   //0, 1, 2
      }
      alert(i);   Error: i is not defined
      )
```

> 인라인 변수 선언 대신, 정의되어 있는 변수를 사용할 수도 있다.

```javascript 
  let i = 0;

      for (i = 0; i < 3; i ++) {  //기존에 정의된 변수 사용
        alert(i);   //0, 1, 2
      }  
      alert(i);   //3, 반복문 밖에서 선언한 변수이므로 사용 할 수 있다.
```

### for문의 구성요소를 생략 할 수 있다.

```javascript
    let i = 0;

    for (; i < 3; i++) {
      alert(i++)    //0, 1, 2
    }

    또는

    let i = 0;

    for(; i < 3;) {
      alert(i++);
    }

    이처럼 생략 가능하다.
```

### 반복문 빠져 나오기

대부분 falsy가 되면 반복문이 종료된다.
특별한 지시자인 **break**를 사용하면 언제든 원하는 때에 반복문을 빠져 나올 수 있다.

### 다음 반복으로 넘어가기

**continue**지시자는 break의 '가벼운 버전'이다. continue는 전체 반복문을 멈추지 않는다. 대신에 현재 실행중인 이터레이션을 멈추고 반복문이(조건울 통과할 때) 다음 이터레이션을 *강제*로 실행시키도록한다.

```javascript
    for (let i = 0; i < 10; i++) {

      //조건이 참이라면 남아있는 본문은 실행되지 않는다.
      if (i % 2 == 0) continue;

      alert(i);   //1, 3, 5, 7, 9가 차례대로 출력
    }

    for (int i = 0; i < 10; i++) {
      if (i == 5)
      continue;
      system.out.printLn("coding Everybody" + i);
    }

    i가 (5 == 5)라고 했을때 조건식에 맞으니까 break처럼 중단되고 출력되지 않는다.
    그리고 다시 for문으로 올라가서 i = 6으로 실행이 되고 (6 == 5) 로 됐을때 조건식이 falsy가 되면서 출력으로 넘어가서 출력된다. 

    ==> 조건식에 맞으면, 출력되지 않고 강제로 다음으로 넘어가서 진행된다. 
    조건식에 맞지 않으면, 출력된다.
```

> continue는 중쳡을 줄이는데에 도움을 준다...

### break/continue와 레이블

여러개의 중첩 반복문을 한 번에 빠져 나와야 하는 경우

```javascript
    labelName: for (...) {
      ...
      break labelName;
    }
```

반복문 안에서 콜론과 함께 쓰이는 식별자를 사용한다.

