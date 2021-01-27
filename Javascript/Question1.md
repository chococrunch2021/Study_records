<small> 질문 목록은 [프론트엔드 면접 핸드북](https://github.com/yangshun/front-end-interview-handbook/blob/master/contents/en/javascript-questions.md "프론트엔드 면접 핸드북") 에서 골랐습니다.</small>

<br/>

### 목차 리스트

- [이벤트 위임](#이벤트-위임-event-delegation이란)

### `이벤트 위임 (event delegation)`이란?

- DOM EVENT가 발생하면 상위 요소까지 전파되는 현상인 `이벤트 버블링을 이용하여 부모 요소에서 이벤트를 처리하는 방법`이다.

- `이벤트리스너를 부모 요소에 건다.` 하위 요소에 이벤트가 발생하면 이벤트 버블링으로 인하여 부모 요소까지 이벤트가 전달되어 부모 요소에 걸어둔 이벤트 리스너가 실행된다.

- 장점
  1. 사용하는 메모리 양의 감소 (모든 요소에 이벤트 걸 필요 없이 상위 요소에만 걸면 된다)
  2. 하위 요소들을 삭제, 추가할 때 이벤트를 새로 추가하고 삭제할 필요가 없다.

### javascript this에 대해서 설명해라

### AMD vs CommonJS

### 객체 변경을 막는 방법

### .forEach와 .map()의 차이

### 이벤트 루프에 대해 설명해라 (Event Loop)

### 호이스팅에 대해 설명해라

### `load`이벤트를 왜 쓰는가? 단점이 있는가? 대안이 있다면 어떤 것이고 왜 쓰는가

### Document의 `DomContentLoaded`와 `Load` 이벤트의차이

### mutable과 immutable 객체의 차이는?

### 동기, 비동기 함수의 차이점은?

### let, var, const의 차이는?
