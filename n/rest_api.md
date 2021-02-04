### REST(ful) API

> REST 아키텍처의 제약 조건을 준수하는 API

- REST는 프로토콜이나 표준이 아닌 `아키텍처 원칙세트`이다
- `리소스 상태에 대한 표현`을 요청자에게 전송한다
- JSON, HTML, XLT, 일반 텍스트 등 여러 형식으로 전송된다

> 기준

- 구성은 클라이언트, 서버, 리소스. `요청이 HTTP로 관리`되는 클라이언트-서버 아키텍처
- `stateless` 클라이언트-서버 대화

  - `클라이언트 정보가 저장되지 않고` 각 요청은 분리되어 있다

- 클라이언트-서버 작용 간소화하는 `캐시 가능`한 데이터
- 정보가 표준 형식으로 전송되기 위한 구성 요소간 표준 인터페이스

  - 요청된 리소스가 식별 가능. 클라이언트에 전송된 표현과 분리
  - 클라이언트가 리소스 조작 가능해야 된다
  - 클라이언트에 반환되는 `self-descriptive 메세지`에 클라이언트가 정보를 어떻게 처리할 지 설명하는 정보가 충분히 포함되어야 한다
  - 하이퍼 미디어:클라이언트가 리소스에 액세스한 후 하이퍼링크를 통해 현재 수행 가능한 모든 작업을 찾을 수 있어야한다

- 요청 정보 검색하는데 관련된 서버의 각 유형을 클라이언트가 볼 수 없는 계층화한다
- code on demand (선택사항): 요청 받으면 서버에서 클라이언트로 실행가능한 코드로 전송해 클라이언트 기능 확장 가능

---

- 기준을 따라야 하지만 더 무거운 XML 메세징, 빌트인 보안이나 트랜잭션 컴플라이언스처럼 요구 사항이 있는 SOAP 프로토콜(Simple object access protocol) 보다 사용하기 쉽다
- 더 빠르고 경량화되어 IoT나 모바일 앱 개발에 적합하다

- [REST와 SOAP 차이 비교하기](https://www.redhat.com/ko/topics/integration/whats-the-difference-between-soap-rest)

---

- 출처
  - [https://www.redhat.com/ko/topics/api/what-is-a-rest-api](https://www.redhat.com/ko/topics/api/what-is-a-rest-api)
  - [https://meetup.toast.com/posts/92](https://meetup.toast.com/posts/92)
