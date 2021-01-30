### HTTP

> 웹 상에서 클라이언트, 서버 간에 요청/응답으로 데이터 주고받을 수 있는 프로토콜

- HTTP메소드는 서버가 요청을 수행하기 위해 해야할 행동을 표시하는 용도로 사용

### GET

> 서버로부터 정보를 조회하기 위해 설계된 메소드

- 요청을 전송할 때 필요한 데이터를 body에 담지 않고 쿼리스트링을 통해 전송한다
- 쿼리스트링: URL 끝에 ?이름=값 쌍을 이루는 요청 파라미터
- 쿼리스트링이 여러개라면 &연산을 사용한다

```
www.example-url.com/resources?name1=value1&name2=value2
```

- 불필요한 요청을 제한하기 위해 캐시될 수 있다
- js,css, 이미지 같은 정적 컨텐츠는 데이터 양이 크고 변경될 일이 적어 동일한 요청을 보낼 필요가 없다

### POST

> 리소스를 생성, 변경하기 위해 설계

- 전송해야 될 데이터를 HTTP 메세지의 BODY에 담아서 전송한다
- BODY는 길이의 제한없이 데이터 전송가능
- GET과 달리 대용량의 데이터 전송가능하다
- 내용이 눈에 보이지 않아 GET보다 보안에서 안전하다고 하지만 크롬 개발자도구나 fidder 같은 툴로 요청 내용 확인 가능 => 민감한 데이터는 반드시 암호화필요
- 요청 헤더 Content-Type에 요청 데이터 타입을 표시해야 한다

### 차이점

- GET은 idempotent하게 POST는 non-idempotent하게 설계됨
- 멱등(idempotent)는 연산을 여러번 적용하더라도 결과가 달라지지 않는 것이다
- get은 서버에 동일한 요청을 여러번 하더라도 동일한 응답이 돌아와야한다는 것
- post는 대용량 데이터를 보내기 좋고 get보다는 좀 더 보안이 좋다

### PUT VS PATCH

- PUT: 리소스의 모든 것을 업데이트
- PATCH: 리소스의 일부를 업데이트

---

- 출처
  - [https://hongsii.github.io/2017/08/02/what-is-the-difference-get-and-post/](https://hongsii.github.io/2017/08/02/what-is-the-difference-get-and-post/) -[https://mangkyu.tistory.com/17](https://mangkyu.tistory.com/17)
