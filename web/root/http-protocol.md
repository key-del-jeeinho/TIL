# HTTP | 2021-10-05
## What is Http?
> HTTP 가 뭐죠?

HTTP 는 `HypertextTransferProtocol` 의 약자로, 인터넷상에서 **서버/클라이언트 모델** 을 따르는 프로토콜이다.

어플리케이션 레벨의 프로토콜로, **TCP/IP 프로토콜 위에서 작동한**다.

HTTP 는 **어떤 종류의 데이터든지 전송**할 수 있도록 설계되어있다. (HTML, IMG, TXT 등)

## How it works?
> HTTP 는 어떻게 작동할까요?

HTTP는 서버/클라이언트 모델을 따른다.
즉, 클라이언트가 보낸 요청(request)을 서버에서 처리하고 응답(response)한다.

![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Ft1.daumcdn.net%2Fcfile%2Ftistory%2F99E63F4B5B6FCA4A01)

- 클라이언트 : 네트워크를 통해 서버에 접속할 수 있는 응용 프로그램 혹은 서비스
- 서버 : 클라이언트의 요청을 받아서, 요청을 해석하고 응답을 하는 원격 서비스

## Connectionless and Stateless
> HTTP 는 비연결성 과 무상태성을 가지고 있습니다. 근데 그게 뭐에요?
### 비연결성
클라이언트와 서버가 한번 연결을 맺은 후, 클라이언트의 요청에 대해 서버가 응답을 마칠경우 **맺었던 연결을 끊어버리는 성질**을 말한다.

- 장점 
    - 연결을 유지하기 위한 리소스가 필요없어진다
    - 즉, 불특정 다수의 통신환경을 기반으로 설계된 HTTP 에서 더 많은 연결을 할 수 있게된다. (필요없어진 리소스를 해당 역할로 사용할 수 있으므로)
- 단점
    - 서버가 클라이언트를 기억하고 있지 않아, 같은 클라이언트의 모든 요청에 새로 연결과 연결해제 과정을 거쳐야한다. 즉, **연결/해제 에 대한 OverHead**가 발생할 수 있다.
    - 연결을 끊어버리기때문에, 클라이언트의 이전 상태를 알 수 없어, **stateless 를 강요**한다.
- KeepAlive
    
    연결/해제 에 대한 OverHead 를 줄이기 위해 Http 의 KeepAlive 속성이 탄생했다.
    
    KeepAlive 란, 지정된 시간동안 서버와 클라이언트 사이에서 패킷교환이 없을경우, 

    상대방의 연결여부를 묻기위해 패킷을 주기적으로 보내는것을 말한다.

    이 때, 패킷에 반응이 없으면 연결을 해제한다.

    _주기적으로 클라이언트의 상태를 체크하므로, 메모리를 많이 사용한다_
### 무상태성
클라이언트가 서버에게 보낸 어떠한 이전 요청과도 무관한 각각의 요청을 **독립적인 트랜잭션으로 취급하는 성질**을 말한다. 

즉, 서버가 클라이언트의 정보를 저장하거나 관리하지 않는다.

따라서, 서버의 확장 (Scailing) 이 자유롭다.

## HTTP Request and Response
> HTTP 프로토콜은 어떻게 데이터를 주고받을까요?

HTTP 프로토콜로 데이터를 주고받으려면 브라우저(Client) 가 서버에 요청(Request)을 보내고 응답(Response)을 받아야한다.

![](https://joshua1988.github.io/images/posts/web/http/request-response.png)

### URL
> 우리가 흔히 주소라 말하는 "이것"

Uniform Resource Locators 의 약자로, **서버에 자원을 요청하기 위해** 입력하는 영문주소이다. 

숫자로 이루어진 IP 주소보다 가독성 등이 높다.

_URL 의 구조_

![](https://joshua1988.github.io/images/posts/web/http/url-structure.png)

### HTTP Requst Method
서버에게 **요청의 종류를 알려주기 위해** 사용한다

- GET : 정보를 요청하기 위해 사용한다.
- POST : 정보를 밀어넣기 위해 사용한다.
- PUT : 정보를 업데이트하기 위해 사용한다.
- DELETE : 정보를 삭제하기 위해 사용한다.
- HEAD : 서버의 헤더정보를 요청한다. 해당 자원이 존재하는지 혹은 서버에 문제가 없는지를 확인하기 위해서 사용한다.
- OPTION : 웹서버가 지원하는 메서드의 종류 등의 서버옵션 을 요청한다. (cors 확인작업 에서도 사용)
- TRACE : Client의 요청을 그대로 반환(echo)한다. 주로 서버 상태를 확인하기 위한 목적으로 사용한다.

### Request Data Format
1. HTTP Request Methd : GET, PUT, POST, PUSH, OPTION 등의 요청방식이 온다.
2. 요청 URI : 요청하는 자원의 위치를 명시한다
3. HTTP 프로토콜 버전 : 웹브라우저가 사용하는 HTTP 버전이다
### Response Header Format
- 프로토콜과 읃답코드 (HTTP/1.1 200 OK)
- 날짜 (Date: Tue, 5 Oct 2021 11:30:00 GMT)
- 서버 프로그램및 스크립트 정보 : (Apache/2.2.4 (Unix) PHP/5.2.0)

그외 다양한 정보들을 헤더로 추가할 수 있다
### Response Code
Response 에서의 Request Method 이다. 서버에서 설정해주는 응답에 대한 분류이다

|num|name|description|
|:---:|:------|:----------|
|200|OK|요청이 성공적으로 수행됨|
|204|No Content|요청이 성공적으로 수행되었으나, 응답 본문에 데이터가 없음|
|400|Bad Request|잘못된 요청|
|401|Unauthorized|요청 권한이 없음 (Authorizeation 헤더가 잘못된 경우|
|403|Forbidden|서버에서 해당 자원에 대해 접근을 금지함|
|500|Internal Server Error|서버측에서 오류가 발생함|
|501|Not Implemented|요청한 동작을 서버가 수행할 수 없음|


_HTTP 프로토콜을 사용한 서버/클라이언트간 통신_
![](https://joshua1988.github.io/images/posts/web/http/http-full-structure.png)

## Tree's Leaf | 좀 더 깊게 파고들 것들
- What is "Protocol"
- What is "TCP/IP"
- What is "Hypertext"
- What is "서버/클라이언트 모델"
- What is "어플리케이션 레벨"
- What is "OverHead" and "Scailing"
- Details of "HTTPMethod"