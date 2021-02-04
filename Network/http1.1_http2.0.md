### http/1.1이 느린이유

- 비연결성으로 연결당 하나의 요청과 응답을 처리하기 때문에 동시 전송 문제와 다수의 리소스를 처리하기에 속도와 성능 이슈 존재

  - HOL(head of line) blocking (특정 응답의 지연)
  - 처음에 요청한 request에 문제가 있어서 2,3번째에 요청한 응답도 같이 늦어지는 문제점도 발생한다
  - RTT(Round Trip Time) 증가 (양방향 지연)
  - 헤더가 크다 (특히 쿠키부분)
  - http/1.1 헤더에는 많은 메타 정보가 저장됨
  - 사용자가 방문한 웹 페이지에 다수의 http 요청이 발생하는데 매 요청시마다 중복된 헤더 값을 전송하며 각 도메인에 설정된 쿠키 정보도 매 요청시마다 헤더에 포함되어 전송된다

### 속도 해결 노력

    - 이미지 스프라이트 (큰 이미지 하나를 받아서 css로 잘라서 사용하는 방법 등)
    - 여러 개의 이미지를 하나의 이미지로 합쳐서 사용
    - 도메인 샤딩
    - 리소스를 여러 개의 도메인으로 나누어 저장해 페이지 로드 시간을 줄인다
    - 여러 개의 도메인으로 나누어진 리소스를 다운받아서 브라우저는 더 많은 리소스를 한번에 많이 받을 수 있다
    - css/javascript 압축 (리소스 요청 수를 줄이는 방법)

### HTTP/2.0 등장

> 요약

    - SPDY 기반으로 등장
    - Multiplexed streams (한 커넥션에 여러 개의 메세지를 동시에 주고받는다. 도메인 샤딩이 필요없게 되었다.)
    - 요청이 커넥션 상에서 다중화되므로 HOL Blocking이 발생하지 않는다
    - stream prioritization(요청 리소스간 의존관계 설정)
    - header compression (헤더정보를 hpack 압축 방식 이용해 압축 전송)
    - server push(HTML 문서 상에 필요한 리소스를 클라이언트 요청없이 보내줄 수 있다)
    - 페이지 로딩 속도 향상
    - 프로토콜 협상 메커니즘 (선택할 수 있음)
    - HTTP/1.1과 높은 수준의 호환성 -메소드, 상태코드, URI, 헤더 필드

---

- 출처
  - [https://lalwr.blogspot.com/2019/01/http1-vs-http2.html](https://lalwr.blogspot.com/2019/01/http1-vs-http2.html)
  - [https://lalwr.blogspot.com/2019/01/http1-vs-http2.html](https://lalwr.blogspot.com/2019/01/http1-vs-http2.html)
    - _추천_ -[https://americanopeople.tistory.com/115](https://americanopeople.tistory.com/115)
