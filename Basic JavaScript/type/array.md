# 배열

첫 번째요소, 두 번째 요소, 세번째 요소 등과 같이 순서가 있는 컬렉션이 필요할때 사용한다.
> 배열 요소의 자료형에는 제약이 없다.

## 배열선언
---
- 첫번째 방법
```javascript
    let arr = new Array();
    let arr = [];
```
- 두번째 방법
```javascript
    let fruits = ["사과","오렌지","귤"];

    alert(fruits[0]);   //사과
    alert(friuts[1]);   //오렌지
    alert(fruits[2]);   //귤
```

## 배열수정하기
---
```javascript
    수정
    fruits[2] = '배';     //사과,오렌지,배 로바뀜

    추가
    fruits[3] = '레몬';   //사과,오렌지,배,레몬

    길이알아내기
    .legnth
```

## pop-push / shift-unshift

## 큐
---
- push -> 맨 끝에 요소를 추가한다.
- shift -> 제일 앞 요소를 꺼내 제거한 후 남아있는 요소들을 앞으로 밀어준다. 이렇게 하면 두 번째 요소가 첫 번째 요소가 된다.
> 큐는 선입선출

## 스텍
---
- push -> 요소를 스택끝에 집어넣는다.
- pop -> 스택 끝 요소를 추출한다.
스텍은 이처럼 한쪽끝에 요소를 더하거나 뺄 수 있게 해주는 자료구조이다.
> 스텍은 후입선출

## 성능
---
> push와 pop은 빠르고 , shift와 unshift는 느리다. 동작원리

## for...of 반복문 / for...in 반복문
------

### for...of 반복문
- for of는 요소의 인덱스는 얻을 수 없고 값만 얻을 수 있다. 배열의 요소를 대상으로 반복 작업을 할 때 for of가 선호된다.

```javascript
  let fruit = ["사과","오렌지","귤"]
  for (let fruit of fruits) {
    alert(fruit);
  }
```
### for...in 반복문
- for in는 모든 프로퍼티를 대상으로 순회하기 때문에 (유사배열(ex length프로퍼티..요소마다 붙어있는 인덱스..키가 숫자형이 아닌 프로퍼티와 메서드..)) '필요없는' 프로퍼티들이 문제를 일으킬 가능성이 생긴다.
- for in 반복문은 배열이 아니라 객체와 함께 사용할 때 최적화 되어있어서 배열과 사용하면 객체에 사용하는것 대비 10~100배 느리다. 배열에는 for in 선호되지 않음

## new Array()

## 다차원 배열
---
```javascript  

  let matrix = [
    [1,2,3],
    [4,5,6],
    [7,8,9]
  ];

  alert(matrix[1][1]);    //5
```

## toString
---
```javascript
    let arr = [1, 2, 3];

    alert( arr ); // 1,2,3
    alert( String(arr) === '1,2,3' ); // true
```