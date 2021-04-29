# 함수

함수는 프로그램을 구성하는 주요 '구성요소'이다. 함수를 이용하면 중복 없이 유사한 동작을 하는 코드를 여러번 호출 할 수 있다.

## 함수선언
---
```javascript
    funtion showMessage() {
      alert('안녕하세요!');
    }

    showMessage();
    showMessage();

    funtion showMessage(parameters) {
      함수 본문...
    }
```

## 지역변수
---
함수 내에서 선언한 변수인 지역변수는 함수 **안에서만** 접근할 수 있다.

```javascript
    function showMessage() {
      let message = '안녕하세요';   //지역변수

      alert(message);
    }

    showMessage();    //안녕하세요

    alert(message);   //오류... message는 지역변수이므로 이 처럼 함수 밖에서 호출할 수 없다.
```

## 외부변수 *
---
함수 내부에서 함수 외부의 변수인 외부변수에 접근할수 있다.

```javascript
    let userName = 'John';

    function showMessage() {
      userName = 'Bob';   //외부 변수를 수정함

      let message = 'Hello,' + userName;
      alert(message);
    }

    alert(userName);    //함수 호출 전이므로 John이 출력

    showMessage();

    alert(userName);    //함수에 의해 Bob으로 값이 바뀜
```

외부변수는 지역변수가 없는 경우에만 사용가능 (동일한 이름을 가진 지역변수일 경우 내부변수만 수정가능하고 외부변수는 변동X)

```javascript
    let userName = 'Oh';

    funtion showMessage() {
      let userName = 'Nana';    //같은 이름을 가진 지역변수를 선언(userName)

      let message = 'Hello, ' + userName;   //Nana
      alert(message);
    }

    showMessage();    //Hello, Nana
    alert(userName);    //함수는 외부변수에 접근X 따라서 값(Oh)이 변경되지 않음
```

## 전역변수
---
함수 외부에 선언된 변수는 전역변수라고 부른다.
전역변수는 같은 이름을 가진 지역 변수에 의해 가려지지만 않으면 모든 함수에서 접근할 수 있다.

변수는 연관되는 함수 내에선언, 전역변수는 되도록 사용하지 않는 것을 권장.
다만 프로젝트 전반에 사용되는 데이터는 전역변수에 저장하는 것이 유용한 경우도 있다.(공유성?? 때문에그런가??)

## 매개변수
---
**매개변수(parameter)** 를 이용하면 임의의 데이터를 함수 안에 전달할 수 있다. 

```javascript
    function showMessage(from, text) { 
      alert(from + ': ' + text);
    }

    showMessage('Ann,' 'Hello');          //Ann, Hello 이게 인수아닌가??
    showMessage('Ann,' 'what's up?');
```

아래 예시를 보면 변경 사항은 외부변수 from에 반영되지 않았다. 함수는 언제나 복사된 값을 사용한다.

```javascript
    funtion showMessage(from, text) {
      
      from = '*' + from '*';

      alert(from + ': ' + text);    
    }
    
    let from = 'Ann';

    showMessage(from,'Hello');    //*Ann*: Hello

    alert(from);                  //Ann
```

## 기본값
---
매개변수에 값을 전달하지 않으면 그 값은 undefined가 된다. 

```javascript
    showMessage(from, text)     //매개변수가 2개이지만 아래와 같이 인수를 하나만 넣어서 호출 할 수 있다.
    
    showMessage('Ann');         //Ann: undefined가 출력
```

만일, undefined가 되지 않게 하고 싶으면 기본값(default value)을 설정해주면 된다.
방법은 매개변수 오른쪽에 '='를 붙이고 undefined 대신 설정하고자 하는 기본값을 써주면 된다.

```javascript
    funtion showMessage(from, text = 'nothing') {
      alert(from + ':' + text);
    }

    showMessage('Ann');   //Ann: nothing
```

함수로 할 수 도 있다.

```javascript
    funtion showMessage(from, text = anotherFuntion()) {
      (. . .)
    }
```

## 매개변수 기본값을 설정할 수 있는 또 다른 방법
---
함수 선언부에서 매개변수 기본값을 설정하는 것 대신 함수가 실행되는 도중에 기본값을 설정하는게 논리에 맞는경우도 생긴다.

```javascript
    1)
    funtion showMessage(text) {
      if(text === undefined) {
        text = '빈문자열';
      }

      alert(text);
    }
    showMessage()   //빈 문자열

    2)
    funtion showMessage(text) {
      text = text || '빈 문자열';
      (. . .)
    }

    3)
    funtion showCount(count) {
      alert(count ?? 'unknown');
    }

    showCount(0);   //0
    showCount(null);    //unknown
    showCount();    //unknown
```

## 반환값
---
함수를 호출했을 때 함수를 호출한 그 곳에 특정 값을 반환(return)하게 할 수 있다.

```javascript
    funtion sum(a,b) {
      return a + b;
    }

    let result = sum(1,2);
    alert(result);  //3;
```

실행 흐름이 지시자 return을 만나면 함수실행은 즉시 중단되고 함수르르 호출한 곳에 값을 반환한다. 위 예시에선 반환 값을 result에 할당하였다.

함수 하나에 여러개의 return문이 올 수도 있다. (if문 같은 경우에 else if(return), else if(return)...)

return만 단독으로 명시하는 것도 가능하다. 이럴때는 함수가 즉시 종료된다.

- return문이 없거나, return지시자만 있는 함수는 undefined를 반환한다.

- 함수는 주석처럼 사용해야한다. (간결하고 명료하게 작성, 타인이 봤을때도 무슨 정의의 함수구문 이구나를 명확히 알아볼 수 있어야 한다.)
