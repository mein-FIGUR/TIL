# HTTP & HTTPS

- HTTP
  - HTTP의 정의
  - HTTP의 특징
  - HTTP의 문제점
- HTTPS
  - HTTPS의 정의
  - 공개키/개인키
- HTTP, HTTPS의 차이

<br>

<br>

## HTTP❓

> HTTP란 HypterText Transfer Protocol의 약자로, 웹 상에서 클라이언트와 서버가 서로 정보를 주고받을 수 있는 프로토콜입니다. TCP/IP 기반으로 서버와 클라이언트 간의 요청과 응답을 전송한다. HTTP에서는 80번 포트를 통해 클라이언트는 자원을 요청하고, 서버는 자원을 제공한다. 

![img](http://blog.wishket.com/wp-content/uploads/2021/02/1.png)

<br>

### HTTP의 특징🔍

- TCP 기반의 통신
- 비연결 지향 (connectionless)
  - 서버는 요청에 대한 응답을 보낸 후 연결을 끊음
- 무상태 (stateless)
  - 연결을 끊는 순간 클라이언트와 서버 간의 통신이 끝나며 상태 정보가 유지되지 않음
  - 클라이언트와 서버가 주고 받는 메세지들은 서로 완전히 독립적
- 클라이언트와 서버의 지속적인 관계 유지를 위해, **쿠키**와 **세션**이 존재 

<br>

### HTTP의 문제점⚠

- 완전성을 증명할 수 없어 변조 가능
- 도청 가능
- 통신 상대를 확인하지 않기에 위장 가능



<br>

<br>

## HTTPS❓

> HTTPS란 HyperText Transfer Protocol over Secure socket layer의 약자입니다. 일반 HTTP 프로토콜에서는 서버에서 브라우저로 전송되는 정보가 암호화되지 않는다는 문제점이 존재하였는데, 이를 SSL이나 TSL 프로토콜을 활용해 보안을 강화시킨 프로토콜이다. 즉, HTTP에 데이터 암호화가 추가된 프로토콜이라고 볼 수 있으며, HTTPS에서 HTTP는 SSL과 통신하고, SSL이 TCP와 통신하게 된다. HTTP와 다르게 443번 포트를 활용하며, 네트워크 상에서 중간에 제 3자가 정보를 볼 수 없도록 공개키 암호화를 지원하고 있다. 
>
> HTTPS는 HTTP 자체를 암호화하는 것이 아니라, HTTP를 사용해서 운반하는 내용(Body)를 암호화한다. HTTP Header는 암호화하지 않는다.

- SSL이 점차 폭넓게 사용되면서, 표준화 기구인 IETF의 관리로 TLS라는 이름으로 바뀌었다.
  - TLS 1.0은 SSL 3.0을 계승함
- SSL(TLS)에서 사용하는 인증서로 상대방을 확인

![HTTP vs HTTPS 차이 HTTPS 개념](http://blog.wishket.com/wp-content/uploads/2020/02/03-3.png)



<br>

### 공개키/개인키🔍

- HTTPS는 공개키/개인키 암호화 방식을 사용하여 데이터를 암호화하며, 공개키와 개인키는 서로를 위한 1쌍의 키이다.
- HTTPS에서는 대칭키 암호화 기법을 사용한다.
  - 공개키의 신뢰성을 위해 CA 인증서를 사용
  - 인증 과정
    1. 서버의 공개키를 인증 기관(CA)에 등록
    2. 인증 기관은 해당 서버의 유효성을 판단한 후, **인증 기관의 비밀키로 서버의 공개키에 디지털 서명으로 공개키 인증서를 작성** 후 등록
        **`공개키 인증서` = `서버의 공개키` + `인증 기관의 디지털 서명 `+ `암호화 된 사이트 정보`**
       인증 기관의 공개키는 사전에 브라우저에 내장되어 있음
    3. 클라이언트가 서버에 접속요청을 하면 서버는 인증 기관에서 받은 인증서를 전송
    4. 클라이언트는 **브라우저에 내장된 인증 기관의 공개키로 디지털 서명을 검증해 신뢰할 수 있는 공개키인지 확인**
    5. 클라이언트는 대칭키 생성(공개키, 비밀키)
    6. 클라이언트는 생성한 **공개키를 서버의 공개키로 암호화해 서버에게 전송**
    7. 서버는 자신의 **비밀키로 해당 내용을 복호화하고 그 대칭키를 가지고 리소스 교환**



<br>

<br>

## HTTP, HTTPS의 차이(정리)✔

- HTTP는 암호화가 추가되지 않아 보안에 취약함
- HTTPS는 안전하게 데이터를 주고 받을 수 있음
- HTTPS는 HTTP에 비해 처리 속도가 느림
  - SSL을 통해 통신이 이루어지는 과정에서 리소스를 소비하며, 통신 속도가 떨어짐
  - 최근에는 CPU의 성능 향상, 메모리의 용량 증가로 속도의 차이가 줄어듦

- HTTPS는 인증서를 발급하고, 유지하기 위한 추가 비용 발생



<br>

<br>

<br>



### REFERENCE

- [(Web) HTTP와 HTTPS 및 차이점][https://mangkyu.tistory.com/98]

- [HTTP, 그리고 HTTPS의 이해][http://blog.wishket.com/http-%ea%b7%b8%eb%a6%ac%ea%b3%a0-https%ec%9d%98-%ec%9d%b4%ed%95%b4/]

- [HTTP VS HTTPS 차이, 알면 사이트의 레벨이 보인다][http://blog.wishket.com/http-vs-https-%EC%B0%A8%EC%9D%B4-%EC%95%8C%EB%A9%B4-%EC%82%AC%EC%9D%B4%ED%8A%B8%EC%9D%98-%EB%A0%88%EB%B2%A8%EC%9D%B4-%EB%B3%B4%EC%9D%B8%EB%8B%A4/]

- [HTTP, HTTPS][https://github.com/WooVictory/Ready-For-Tech-Interview/blob/master/Network/HTTP%2C%20HTTPS.md]

