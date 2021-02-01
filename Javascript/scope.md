### 스코프

> 참조대상식별자(확인자)를 찾아내기 위한 규칙이다.

```

var x = 'global';

function foo () {
  var x = 'function scope';
  console.log(x);
}

foo(); // ?
console.log(x); // ?

```

- 변수 x를 참조할 때 중복된 2개의 x변수 중 어떤 변수를 참조할 것인가?

- 식별자는 `자신이 어디에 선언되었는가`에 따라 자신을 참조할 수 있는 유효한 범위를 갖는다 (렉시컬 스코프)

- 함수나 코드 블록은 중첩될 수 있다. 함수 foo내에서 선언된 변수 x는 foo 내부에서만 참조할 수 있고 함수 외부에서는 참조할 수 있다. 스코프는 이런 규칙의 집합인 것이다.

- 스코프가 없다면 어떻게 되는가? 같은 식별자 이름 x는 충돌을 일으킬 것이다.
  즉, 전체 프로그램에서 변수x는 하나만 사용하게 된다. 폴더라는 것이 없다면 같은 이름의 파일을 하나만 만들 수 있는 것과 같다.
- 이처럼 스코프도 식별자 이름의 충돌을 방지한다.

### JS 스코프 특징

- 자바스크립트는 기본적으로 함수 레벨 스코프를 갖는다. function(){}
- ES6부터 등장한 let과 const 변수는 블록 레벨 스코프 {} 를 갖는다.

```

let y = 0;
{
  let y = 1;
  console.log(y); // 1
}
console.log(y);   // 0

```

### 지역변수 > 전역 변수

```

var x = 'global';

function foo() {
  var x = 'local';
  console.log(x);

  function bar() {  // 내부함수
    console.log(x); // ?
  }

  bar();
}
foo();
console.log(x); // ?

```

bar 내부의 x는 foo내부의 변수 x를 참조한다. 실행컨텍스트의 스코프 체인에 의해
참조 순위에서 전역변수 x가 foo의 지역변수 x에게 밀렸기 때문이다.

### 렉시컬 스코프

```
var x = 1;

function foo() {
  var x = 10;
  bar();
}

function bar() {
  console.log(x);
}

foo(); // ?
bar(); // ?

```

- bar의 상위 스코프가 어디인지에 따라서 결정된다.
- foo내부에서 bar이 호출되어도 bar가 정의된 위치는 전역스코프 안이다.
- `함수를 어디서 선언했는가에 따라 상위 스코프가 결정`되는 `렉시컬 스코프` 원칙에 따라 둘 다 전역 변수인 1을 출력한다.
- 이와 반대로 함수를 어디서 호출했는 가에 따라 상위 스코프가 결정되는 것은 동적 스코프 방식이다.

### 암묵적 전역 implicit global

```
var x = 10; // 전역 변수

function foo () {
  // 선언하지 않은 식별자
  y = 20;
  console.log(x + y);
}

foo(); // 30

```

- y 변수를 선언하지 않았지만 에러가 나지 않는다.
- foo 함수가 호출되면 자바스크립트 엔진은 변수 y에 값을 할당하기 위해 스코프 체인을 통해 y를 찾아나선다.
- foo함수의 스코프와 전역 스코프 어디에서도 y의 선언을 찾을 수 없다. 그러면 자바스크립트 엔진은 y=20을 window.y=20으로 해석하여 동적으로 프로퍼티를 생성한다. (암묵적 전역)
- y는 변수가 아니라 전역 객체의 프로퍼티가 되어 호이스팅이 일어나지 않는다. 프로퍼티이므로 delete 연산자로 삭제할 수 있다.

```

// 전역 변수 x는 호이스팅이 발생한다.
console.log(x); // undefined
// 전역 변수가 아니라 단지 전역 프로퍼티인 y는 호이스팅이 발생하지 않는다.
console.log(y); // ReferenceError: y is not defined

var x = 10; // 전역 변수

function foo () {
  // 선언하지 않은 변수
  y = 20;
  console.log(x + y);
}

foo(); // 30

```

---

- 출처
  - [https://poiemaweb.com/js-scope](https://poiemaweb.com/js-scope)
