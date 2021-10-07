# Protocol | 2021-10-07
## What is Protocol?
> Protocol 이 뭔가요?

구글번역에 Protocol을 치면 **규약** 이라고 번역된다
![](https://cdn.discordapp.com/attachments/736846956504285194/895609962154303498/unknown.png)
- 프로토콜 즉, 통신 프로토콜이란 컴퓨터 또는 그외 **원거리 통신 장비 사이에서 메세지를 주고받는 양식과 규칙의 체계**이다. 
- 통신 프로토콜은 신호체계, 인증, 그리고 오류 감지 및 수정기능을 포함할 수 있다.
- 프로토콜은 IEEE, ISO 등의 기관에서 정의한다
- 가장 널리쓰이는 웹 프로토콜로는 [HTTP](https://github.com/key-del-jeeinho/TIL/blob/main/web/http-protocol/http-protocol.md) 가 있다

## Functions of Protocols
> Protocol 은 어떤 역할을 할까요?
프로토콜은 다음과 같은 기능을 수행한다
- Addressing (주소설정)

    한 개체가 상대 개체에 데이터를 전송하려면 상대의 이름을 알아야 하는데, 프로토콜에는 **각 전송계층에 맞는 주소를 지정하는 기능**이 있다. 이를 주소설정이라고 한다.
- Sequence Controll (순서제어)

    프로토콜 데이터 단위가 **전송될 때 보내지는 순서를 명시**하는 기능이며, 연결 지향형 (Connection Oriented) 프로토콜에만 사용된다.
    - 프로토콜 데이터 단위 (Protocol Data Unit) 

        데이터가 전송될 때 일정크기의 데이터 블록을 말한다.

    순서를 지정하는 이유는 **흐름제어 및 오류제어 등의 역할을 수행하기 위함**이다.
    PDU 를 상대한테 보낼 경우, 상대는 순서에 맞게 데이터를 재구성하고, 오류가 있을 경우 재전송을 요청한다.
    해커는 순서가 얽힌 패킷을 생성하고 전송해, 시스템 과부하를 발생시키기도 한다.
- Encapsulation (캡슐화)

    PDU 는 SDU(ServiceDU)와 PCI(Protocol Controll Information) 로 구성되어있다.
    - SDU : 전송하려는 데이터
    - PCI : 제어정보

    PCI 에는 주소, 오류 검출 코드, 프로토콜 제어정보 등이 있는데, 이러한 정보를 붙이는것을 캡슐화라고 한다.
    캡슐화는 **해커로부터 자신의 통신내용을 숨길 수 있게 해준다**
- 동기화 (Synchronization)
    데이터를 전송할 때, 각 객체는 타이머 값이나 윈도우 크기 등을 기억해야하는데, 이러한 값을 공유하는것을 말한다

이 이외에도 연결제어, 흐름제어, 다중화 등의 기능이 존재한다

## Tree's Leaf | 좀 더 깊게 파고들 것들
- ComputerScience

