### HTTP (Hypertest Transfer Protocol)

- www상에서 웹 서버와 브라우저가 하이퍼텍스트 데이터를 주고받기 위한 통신 프로토콜
- 기본 TCP/IP포트로 80포트 사용
- 데이터를 단순 텍스트 형태로 주고받기 때문에 네트워크에서 전송 신호를 가로채는 경우 원치 않는 데이터 유출이 발생할 수 있다
- 통신 상대를 확인하지 않아 위장이 가능하다.

### HTTPS (Hypertext Transfer Protocol Secure)

- HTTP의 보안이 광화된 버전. SSL이나 TLS프로토콜을 통해 세션 데이터 암호화한다.
- HTTP에서 주고받는 데이터가 암호화되지 않아 쉽게 도난당하는 문제가 있었다.
- 보안 문제를 해결하기 위해 SSL 도입 (= 현 TLS)
- 공개키를 공개하여 클라이언트 측에서 암호화된 데이터를 서버로 보내면 서버가 비밀키로 복호화한다.
- TLS는 데이터 무결성을 제공하여 데이터가 전송 중에 수정되거나 손상되는 것을 방지하고 사용자가 자신이 의도하는 웹사이트와 통신하도록하는 인증 기능도 제공한다
- 구글 검색 엔진 등에서 HTTPS로 통신하는 웹 페이지에 더 높은 점수를 준다. 즉 SEO에 더 유리하다
- 기본 TCP/IP 포트는 443이다.

### https 단점

- https는 http보다는 암호화/복호화, 인증과정으로 웹 서버에 부하가 생기고 느리다.
- https는 비용이 좀 더 발생한다.
- http는 비연결형으로 웹 페이지를 보다가 인터넷 연결이 끊어졌다 다시 연결되어도 그 페이지를 볼 수 있지만 https의 경우에는 소켓 자체에서 인증을 하여 인터넷 연결이 끊기면 다시 인증과정을 거쳐 시간이 걸린다.
- 중요한 페이지는 https로 아무나 봐도 되는 페이지는 http로 하는 것이 좋다.

---

- 추가로 읽어볼 목록
  - [HTTPS는 HTTP보다 빠르다](https://tech.ssut.me/https-is-faster-than-http/)

---

- 출처
  - [http://blog.wishket.com/http-vs-https-%EC%B0%A8%EC%9D%B4-%EC%95%8C%EB%A9%B4-%EC%82%AC%EC%9D%B4%ED%8A%B8%EC%9D%98-%EB%A0%88%EB%B2%A8%EC%9D%B4-%EB%B3%B4%EC%9D%B8%EB%8B%A4/](http://blog.wishket.com/http-vs-https-%EC%B0%A8%EC%9D%B4-%EC%95%8C%EB%A9%B4-%EC%82%AC%EC%9D%B4%ED%8A%B8%EC%9D%98-%EB%A0%88%EB%B2%A8%EC%9D%B4-%EB%B3%B4%EC%9D%B8%EB%8B%A4/) -[https://kmj1107.tistory.com/entry/Http-vs-Https-Http%EC%99%80-Https%EC%9D%98-%EC%B0%A8%EC%9D%B4%EC%A0%90?category=416059](https://kmj1107.tistory.com/entry/Http-vs-Https-Http%EC%99%80-Https%EC%9D%98-%EC%B0%A8%EC%9D%B4%EC%A0%90?category=416059) -[https://seolhun.github.io/contents/network-http-http-vs-https%EC%9D%98-%EC%B0%A8%EC%9D%B4-%EA%B7%B8%EB%A6%AC%EA%B3%A0-packet%EA%B3%BC-tsl-ssl](https://seolhun.github.io/contents/network-http-http-vs-https%EC%9D%98-%EC%B0%A8%EC%9D%B4-%EA%B7%B8%EB%A6%AC%EA%B3%A0-packet%EA%B3%BC-tsl-ssl)
