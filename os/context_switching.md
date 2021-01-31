### 문맥 교환 context_switching

> CPU가 작업하고 있는 TASK(PROCESS/THREAD)를 실행하다가 인터럽트(시간 초과 등) 가 발생시 다른 TASK로 전환되는 과정에서 기존의 TASK에 대한 상태 정보를 저장하고 (CONTEXT) 새로운 TASK의 CONTEXT 정보로 교체하는 작업

- PCB블럭을 교환하여 CPU를 새로운 PCB블럭에 해당하는 내용으로 환경을 세팅하는 것이다
- PCB는 OS에 의해 스케줄링 되는 프로세스 제어 블록이고 Thread의 경우 프로세스 내 TCB 라는 내부 구조를 통해 관리된다.
- Context switching 시 PCB 정보를 바탕으로 이전에 수행하던 작업이나 신규 작업을 수행할 수 있게 된다.

> Context switching 시 CPU는 캐시와 메모리 매핑을 초기화하는 등의 작업을 거치면서 잦은 Context switching은 오버 헤드를 발생시킨다.

---

- 출처
  - [https://jins-dev.tistory.com/entry/%EC%BB%A8%ED%85%8D%EC%8A%A4%ED%8A%B8-%EC%8A%A4%EC%9C%84%EC%B9%98Context-Switching-%EC%97%90-%EB%8C%80%ED%95%9C-%EC%A0%95%EB%A6%AC](https://jins-dev.tistory.com/entry/%EC%BB%A8%ED%85%8D%EC%8A%A4%ED%8A%B8-%EC%8A%A4%EC%9C%84%EC%B9%98Context-Switching-%EC%97%90-%EB%8C%80%ED%95%9C-%EC%A0%95%EB%A6%AC)
