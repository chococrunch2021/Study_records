### 목차
1. Operating system services
2. System calls
3. Types of system calls
4. operating system structure

## 운영체제에서 제공하는 서비스
![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/337ec8ef-71c5-4d72-9f63-b68efba0d43c/Untitled.png](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F337ec8ef-71c5-4d72-9f63-b68efba0d43c%2FUntitled.png?table=block&id=cd3a2b40-f35e-4dbc-93f9-f8ac7b934b4a&width=3070&userId=db840e06-a071-4f1d-89ea-442ea97f2322&cache=v2)


운영체제는 컴퓨터 프로그램이 실행되는 환경을 제공한다. 

그를 위해서 위와 같은 서비스를 제공한다.

여러 프로그램을 돌리기 위해 멀티 프로세싱을 하게 되고 그런 과정에서 동기화 문제가 발생하며 데드락이 발생할 수 있다.

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0ab5376c-135a-47b5-b2e6-4a0d4cc30271/Untitled.png](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F0ab5376c-135a-47b5-b2e6-4a0d4cc30271%2FUntitled.png?table=block&id=8da3544b-a30e-435e-9188-d18e06fa7df7&width=3070&userId=db840e06-a071-4f1d-89ea-442ea97f2322&cache=v2)

앞으로 (공룡책에서) 주로 배우게 될 서비스 ⇒ `프로그램 실행(관리 부문), file System`

나머지는 상대적으로 마이너하다.

##  운영체제 각 서비스 정리

### UI (유저 인터페이스)

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/61006056-da70-44cb-b6df-c22e0acb3669/Untitled.png](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F61006056-da70-44cb-b6df-c22e0acb3669%2FUntitled.png?table=block&id=fc2e4f04-2655-4a1c-b86c-50f71181f613&width=3070&userId=db840e06-a071-4f1d-89ea-442ea97f2322&cache=v2)

- CLI: 사용자가 텍스트 명령으로 명령을 내리는 방식. (SHELL, MS-DOS, 애플 소프트 베이직)
- 배치 인터페이스: 명령어를 파일에 넣어두고 파일이 실행되면서 명령어를 실행하는 인터페이스.

- GUI: 가장 흔하다. 마우스 클릭, 키보드 등으로 명령 내린다.

### 프로그램 실행 (Program execution)

- 시스템은 프로그램을 메모리에 로드하고 실행할 수 있어야 한다.
- 정상적으로든 비정상적으로든 실행을 완료할 수 있어야한다.

### 입출력 명령 (I/O Operations)

- 프로그램이 필요할 경우 운영체제가 입출력 명령 수행해야한다.
- 사용자가 직접 조작하지 않고 운영체제를 거치도록 한다. (보안)

### 파일 시스템 조작 (File- System manipulation)

- 파일 쓰기, 읽기, 삭제. 사용자의 접근 권한 설정하기도 한다.

### 통신(Communications)

- 한 프로세스가 다른 프로세스와 통신하기 위해서는 운영체제는 공유 메모리(Shared memory)나 메세지 패싱(Message passing) 방법을 사용한다.
- 공유메모리: 여러 프로세스가 `메모리의 한 부분` 공유
- 메세지 패싱: `프로세스간 정보 패킷을 주고 받는 것` ( 더 느림)

### 에러 탐지 (Error Detection)

- 하드웨어, 입출력 장치, 사용자 프로그램의 에러를 탐지하고 수정해야 한다.

### 자원 할당(Resource Allocation)

- 여러 사용자가 여러 작업을 동시에 하기 위해서 자원을 적절히 잘 분배해야 한다.

### 회계

- 어떤 유저가 어떤 자원을 얼마나 사용하는지 계속 추적한다.

### 보호 보안

- 접근 권한, 사용자 권한 관리

### 시스템 콜 fork(), fopen()

- 커널과 사용자 프로그램을 이어주는 인터페이스

- 운영체제의 서비스를 사용할 수 있게 해주는 인터페이스

1. 사용자가 OS와 상호작용하는 방법

1) CLI : 명령어 기반으로 상호작용하는 방법 (쉘 이용)

2) GUI: 대표적으로 마우스

3) 터치 스크린 동작 : 안드로이드 등

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/61006056-da70-44cb-b6df-c22e0acb3669/Untitled.png](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F61006056-da70-44cb-b6df-c22e0acb3669%2FUntitled.png?table=block&id=fc2e4f04-2655-4a1c-b86c-50f71181f613&width=3070&userId=db840e06-a071-4f1d-89ea-442ea97f2322&cache=v2)

2) 컴퓨터 프로그램이 os와 인터페이스 하는 방법: `시스템 콜`

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4cb8d7bd-4951-449b-8851-eb118af68e88/Untitled.png](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F61006056-da70-44cb-b6df-c22e0acb3669%2FUntitled.png?table=block&id=fc2e4f04-2655-4a1c-b86c-50f71181f613&width=3070&userId=db840e06-a071-4f1d-89ea-442ea97f2322&cache=v2)

상호작용하기 위해서 필요한 함수를 호출 ⇒ 시스템 콜 (OS API)

사용자가 일일히 오픈해서 사용하기 귀찮다 ⇒ 라이브러리 사용 

1. 사용자가 시스템에 접근하기 위해서 (open) 커널 모드로 전환되어야 하는데 이때 시스템 콜을 사용한다. 
2. 메모리의 특정 주소 범위에는 어떤 동작들이 할당 되어 있다

    ⇒ `시스템 콜 테이블, 인터럽트 벡터`

    ex. fopen() 함수를 호출 시 운영체제는 이 함수를 찾기 위해 `시스템 콜 테이블`을 참조한다.

    시스템 콜 테이블 ⇒ 메모리 주소의 모음. 해당 메모리 주소는 `인터럽트 서비스 루틴`을 가르킨다.

    인터럽트 서비스 루틴⇒ 일반적으로 C로 짜여짐. 시스템 콜 테이블이 가르키는 특정 메모리 주소가 구체적으로 어떤 동작을 할 지 정의해 놓은 것

대표적인 시스템 콜 함수 `fopen(), exit(), read(), write()` 

직접 조작하기 힘들기 때문에 표준 라이브러리를 사용한다. `stdio.h`.

### 시스템 콜 타입

시스템 콜은 크게 6가지로 분류할 수 있다.

- `프로세스 제어: end, abort, load, execute`
- `파일 관리: create, delete, open, close, read, write`
- 장치 관리: read, write, request, release
- 정보 유지: get/set time or date
- 통신: send/receive messages, transfer status
- 보호

### 현대 운영체제 계층 관리

### Simple Structure

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/63cfcf65-74e3-4f08-8a89-3ed8c6b4356b/Untitled.png](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F63cfcf65-74e3-4f08-8a89-3ed8c6b4356b%2FUntitled.png?table=block&id=ca04a399-4449-4ae3-bc28-5a07ce7e4a52&width=3070&userId=db840e06-a071-4f1d-89ea-442ea97f2322&cache=v2)

- 과거에는 사실상 계층 구분 x

- MS-DOS에서 사용자 프로그램이 입출력 루틴에 접근해 디스플레이와 디스크 드라이브에 `직접 쓰기`를 함. ⇒ 사용자 프로그램에 문제 생기면 전체 시스템에 문제 생김

### 전통적 UNIX 시스템 구조 

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c769ab75-bbb5-44ff-a443-175403bcb4b6/Untitled.png](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fc769ab75-bbb5-44ff-a443-175403bcb4b6%2FUntitled.png?table=block&id=495896d9-1d27-4b3b-acdb-c0c2269e736c&width=3070&userId=db840e06-a071-4f1d-89ea-442ea97f2322&cache=v2)

- MS-DOS에 비해 기능이 분리됨.

- 하나의 계층이 너무 많은 일을 한다.

- 하드웨어와 사용자 계층 사이의 커널이 모든 기능을 제공 ⇒ 모놀리식 구조

- 구현과 유지보수가 쉽지 않았다.

### Layered Approach (계층적 접근 방식)

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/104aff65-5f53-4361-856b-6d2b1932e690/Untitled.png](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F104aff65-5f53-4361-856b-6d2b1932e690%2FUntitled.png?table=block&id=959188e1-fdc2-4112-aa0b-ff8f6148a86d&width=3070&userId=db840e06-a071-4f1d-89ea-442ea97f2322&cache=v2)

- 가장 아래 계층은 하드웨어, 가장 위는 사용자 인터페이스

- 유지보수가 편하다. 하나의 계층만 신경쓰면 다른 계층에는 아무런 신경을 안써도 된다.

### 마이크로 커널

- 커널에서 `핵심적인 요소`만 남긴 가벼운 커널

- 커널이 커질 수록 문제가 생길 가능성이 높아지고 유지보수 힘듬

- 커널보다 코드 양이 적어 컴파일, 테스트 시간이 짧고 `다른 시스템에 이식하기도 쉽다`.

- IoT 등 에서 사용된다.

### 모듈

- 모듈은 커널을 확장하는 기술이다.
- 각 기능들을 독립적으로 관리하여 효과적으로 시스템 유지한다.
- 장치 드라이버는 모두 모듈로 구현되어 있다.

### 하이브리드 시스템

- 커널의 `핵심만 남기고 나머지는 따로 구현`한 시스템

- 안드로이드는 리눅스 커널 위에 자체 구현한 라이브러리를 올린 시스템 

---

### 기타 (동기, 비동기 입출력)

- (제어권을 넘겨주는가) block, non-block   
- (작업완료되었는지 확인을 한다) synchronouse vs asnycronous 

### 동기식 입출력 (Block)

- 입출력 요청 후 호출된 입출력 작업이 완료된 후에야 CPU의 제어권이 호출한 그 프로그램에게 다시 넘어가는 방식
- A가 B를 호출한 경우
    - A는 B작업이 완료되어 B가 A로 제어권을 넘겨줘야만 제어권을 가질 수 있다.
    - B가 제어권을 넘겨줄 때까지 다음 명령을 수행하지 않고 기다린다.

    1. 사용자가 I/O 요청을 하면 동기식 입출력에서는 먼저 운영 체제의 커널로 CPU의 제어권이 넘어와서 입출력 처리와 관련된 커널의 코드가 수행됩니다.
    2. `입출력을 호출한 프로세스의 상태를 봉쇄 상태(block state)로 바꾸어 입출력이 완료될 때까지 CPU를 할당받지 못하도록` 합니다.
    3. 입출력이 완료되면 I/O 컨트롤러가 CPU에게 인터럽트를 발생시켜 입출력이 완료되었음을 알려줍니다.
    4. 그러면 이 프로세스의 봉쇄 상태를 해제시켜 CPU를 할당받을 수 있는 권한이 다시 생기게 됩니다.

### 비동기식 입출력

- 입출력 요청 후 연산이 끝나길 기다리지 않고 CPU 제어권을 호출한 프로그램에게 바로 넘기는 방식
- 할 수 있는 작업 먼저 실행 나중에 실행할 작업들은 후에 수행


### Synchronous 입출력
- A 함수가 B를 호출한 후 B의 작업 결과를 받을 때까지 A가 기다린다.

### Asynchronouse 입출력
- A 함수가 B를 호출한 후 B의 작업 결과 유무를 A가 신경쓰지 않는다.

### 출처 (참고)

[입출력 구조](https://velog.io/@sparkbosing/%EC%9E%85%EC%B6%9C%EB%A0%A5-%EA%B5%AC%EC%A1%B0)

[https://parksb.github.io/article/5.html](https://parksb.github.io/article/5.html)

[https://www.inflearn.com/course/운영체제-공룡책-전공강의/lecture/65690?tab=curriculum&speed=1.5](https://www.inflearn.com/course/%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C-%EA%B3%B5%EB%A3%A1%EC%B1%85-%EC%A0%84%EA%B3%B5%EA%B0%95%EC%9D%98/lecture/65690?tab=curriculum&speed=1.5)

[https://musma.github.io/2019/04/17/blocking-and-synchronous.html](https://musma.github.io/2019/04/17/blocking-and-synchronous.html)