- [브라우저 이벤트 발생](https://tangoo91.tistory.com/33)

  - `캡처링 => 타깃 => 버블링` 단계 순으로 전파된다.

- [브라우저 이벤트2](https://velog.io/@proshy/JS-%EB%B8%8C%EB%9D%BC%EC%9A%B0%EC%A0%80-%EA%B8%B0%EB%B3%B8-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%99%80-%EB%B2%84%EB%B8%94%EB%A7%81-%EB%B0%A9%EC%A7%80)

### 이벤트 처리기

- 이벤트가 발생하는 것을 감지하는 역할

### 이벤트 핸들러

> `하나의 요소`에 `하나의 이벤트` 처리 가능.

- HTML태그에 설정

`<button onclick="onClickFunc()"/>`

- DOM요소 객체의 이벤트 처리기 프로퍼티 설정

```
  const btn=document.getElementById("btn");
  btn.onclick=onClickFunc();

```

- 이벤트 리스너와 달리 `타깃`과 `버블링 단계`에서만 실행된다.

### 이벤트 리스너

> `하나의 요소`에 `복수의 이벤트` 처리 가능. addEventListener

```
btn.addEventListener(eventType,listener(함수),useCapture);
```

- useCapture: true => 캡처링, false=>버블링(default)
- 장점

  - 같은 요소의 같은 이벤트에 이벤트 리스너 여러 개 등록 가능
  - 버블링, 캡처링 단계 모두 활용 가능

- 같은 요소의 같은 이벤트를 등록한다면 버블링 단계에 등록하는 경우 핸들러 => 리스너 순으로 실행된다.

---

- preventDefault()
  - 웹 브라우저 기본 동작 취소(refresh)
- stopPropagation()
  - 이벤트 전파 막음. 다음 요소의 이벤트는 멈추고 같은 요소의 다른 리스터는 정상적으로 실행
- stopImmediatePropagation()
  - 그 다음 요소의 이벤트 전파 및 같은 요소의 다른 이벤트 리스너도 멈춘다
