### HTTP 공통 헤더 - General Header 일반 헤더

> 요청 및 응답 메세지 모두에서 사용가능한 일반 목적의 헤더 항목

- 구성 요소
  - DATE: HTTP메세지 생성한 일시
  - CONNECTION: 클라이언트와 서버 간 연결에 대한 옵션
    - CONNECTION: CLOSE, CONNECTION: Keep-Alive
  - Cache-Control
  - Pragma
  - Trailer

### HTTP 엔티티 관련 헤더

> 엔티티/ 개체 헤더 (Entity header) 항목

- 요청 및 응답 메시지 모두에서 사용가능 한 엔티티(콘텐츠, 본문, 리소스) 등에 관한 설명 헤더 항목
- http메세지 내 포함된 개체에 대한 구체적인 미디어 타입 설명
- http메세지는 이미지, 비디오, 오디오, html문서, 전자메일 등 개체 운반 가능하다

- 구성
  - Content-Type: 미디어 타입 정보
    - 타입 및 서브타입 구성
  - Content-language: 사용자 언어
  - Content-encoding: 개체 데이터 압축 방식

---

- 출처
  - [https://gmlwjd9405.github.io/2019/01/28/http-header-types.html](https://gmlwjd9405.github.io/2019/01/28/http-header-types.html)
