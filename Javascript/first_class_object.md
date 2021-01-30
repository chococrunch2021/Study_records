### 객체란 Object

- 현실 세계의 사물을 코드 상으로 데이터로 표현한 것 (속성과 행위로 표현한다)
- Javascript에서 객체란 `여러 속성을 하나의 변수에 저장`할 수 있도록 해주는 데이터 타입
- `key/value 쌍`으로 데이터를 저장할 수 있는 구조

### Ecmascript 객체 구분

1. javascript 내장 객체 (Built-in Object)

   - javascript 엔진이 구동되는 시점에서 바로 제공된다
   - Global, Object, String,Number, Boolean, Date,Array, Math

2. 브라우저 내장 객체 (Native Object)

   - BOM 브라우저 객체 모델, DOM 문서 객체 모델

3. 사용자 정의 객체 (Host Object)
   - 생성자 함수, 객체 리터럴을 통해 사용자가 정의하고 확장시킨 객체

### 1급 객체

1. 변수나 데이터에 할당할 수 있다
2. 파라미터로 넘길 수 있다
3. 반환 값을 사용할 수 있다
4. 동적으로 프로퍼티에 할당할 수 있다
5. 할당에 사용된 이름과 관계없이 고유한 구별이 가능하다

---

> 변수나 데이터에 할당할 수 있다

```
var foo = function(){
    console.log("익명함수를 foo 변수에 담을 수 있습니다.");
}

foo();
```

> 파라미터로 전달할 수 있다

```
var foo = function(){
    let x = 10;
    return x;
}

var goo = function(value){
    console.log(value)
}

// 인자로 함수를 전달할 수 있습니다.
goo(foo());

```

> 반환 값으로 사용할 수 있다

```
var foo = function(){
    return function(){
        var x = 10;
        return x;
    }
}

console.log(foo())   // 익명함수를 반환합니다.
console.log(foo()()) // 익명함수가 반환하는 값을 반환합니다.

```

> 할당에 사용된 이름과 관계없이 고유한 구별이 가능하다

```
var foo = function goo(){
    console.log("goo라는 함수로 선언했지만 foo라는 변수로 고유 구별이 가능합니다.")
}

foo();

```

> 할당에 사용된 이름과 관계없이 고유한 구별이 가능하다

```
var foo = function goo(){
    console.log("goo라는 함수로 선언했지만 foo라는 변수로 고유 구별이 가능합니다.")
}

foo();

```

> 동적으로 프로퍼티 할당이 가능하다

```

function foo(){
    console.log("foo()함수는 비어 있습니다.")
}

foo.property1 = "첫 번째 프로퍼티 추가";
foo.property2 = "두 번째 프로퍼티 추가";

console.log(foo.property1);
console.log(foo.property2);

```

---

- 출처
  - [javascirpt 객체란](https://velog.io/@surim014/%EC%9B%B9%EC%9D%84-%EC%9B%80%EC%A7%81%EC%9D%B4%EB%8A%94-%EA%B7%BC%EC%9C%A1-JavaScript%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80-part-7-Object-35k01xmdfp)
  - [1급 객체](https://victorydntmd.tistory.com/46)
