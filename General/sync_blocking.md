### blocking vs non-blocking

> 함수 호출 시 제어권을 리턴하는가

- non-blocking
  - 함수 A가 함수 B를 호출한다.
  - 함수 B는 즉시 제어권을 A에게 넘겨준다.
  - A는 B호출 이후 바로 다른 일을 할 수 있다.
- blocking
  - 함수 B가 자신의 작업이 끝날 때까지 A에게 제어권을 넘겨주지 않는다

### synchronous vs asynchronous

> 함수 호출시 호출시킨 함수의 작업 완료를 신경쓰고 있는가

- Synchronous

  - 함수 A가 B를 호출시킨 뒤 제어권을 받든 말든 B의 작업 완료를 기다린다

- Asynchronous
  - 함수 A가 B를 호출시킨 뒤 B의 작업완료를 기다리지 않는다.

---

<br/>

### Sync and blocking (제어권 넘기지 않음. 작업완료 기다림)

- a는 작업 완료 여부를 체크하며 b가 끝나기를 기다린다.

### Sync and non-blocking

> (제어권 넘김. 작업완료를 기다림)

- A는 제어권 넘겨받아 다른 일을 하지만 계속해서 B가 끝났는지 체크를 해준다

### Async and blocking

> (제어권 넘기지 않고 작업완료 기다림)

- A는 다른 일을 하지 않고 B가 끝날 때까지 기다리고 있는다
- MySql + node.js 조합. nodejs가 async 처리를 해도 mysql 드라이브가 blocking 방식이다. 그냥 기다릴 수 밖에

### Async and non-blocking

> (제어권 넘기고 작업완료 기다리지 않음 )

- A는 바로 제어권 넘겨받아 다른 일을 하며 작업완료를 기다리지 않는다

---

<br/>

- 출처
  - [https://homoefficio.github.io/2017/02/19/Blocking-NonBlocking-Synchronous-Asynchronous/](https://homoefficio.github.io/2017/02/19/Blocking-NonBlocking-Synchronous-Asynchronous/)
  - [https://goodgid.github.io/Blocking-NonBlocking-Synchronous-Asynchronous/](https://goodgid.github.io/Blocking-NonBlocking-Synchronous-Asynchronous/)
