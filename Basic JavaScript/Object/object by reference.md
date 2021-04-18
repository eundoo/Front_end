# 참조에 의한 객체 복사

객체와 원시 타입의 근본적인 차이 중 하나는 
*객체*는 **참조에** 의해 저장되고 복사된다.
*원시값은* **값 그대로** 저장,할당되고 복사된다.

## 원시형
---
> 예시를 실행하면 두 개의 독립된 변수에 각 각 문자열 'it was so much fun!' 이 저장된다.

```javascript   
    let messege = 'it was so much fun!'
    let reply = messege;
```

## 객체형
---
> 변수에는 객체가 그대로 저장되는 것이 아니라, 객체가 저장되어있는 **메모리 주소**인 객체에 대한 **참조값**이 저장된다. 따라서 객체가 할당된 변수를 복사할 땐 객체의 참조 값이 복사되고 객체는 복사되지 않는다.

```javascript
    let user = {
      name: 'Nana'
    };
```

![objects](../../images/object_exp.PNG)

![objects](../../images/object_exp2.PNG)

> 따라서 객체에 접근하거나 객체를 조작할 땐 여러 변수를 사용 할 수 있다.

```javascript
    let user = {name: 'Nana'};

    let adim = user;

    admin.name = 'Nana Oh';

    alert(user.name)    //'Nana Oh'가 출력된다.
```

### 참조에 의한 비교 == / ===

```javascript
    let a = {};
    let b = a;    //참조에 의한 복사

    alert(a == b);
    alert(a === b);   둘 다 true (두 변수 같은 객체를 참조하기 때문에)

    --------------------------------------------------------------------------

    let a = {};
    let b = {};

    alert(a == b);    //false (독립된 두 객체이기 때문에)
```

## 중첩 객체 복사
...
