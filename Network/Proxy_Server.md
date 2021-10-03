# Proxy Server

<br>

- Proxy Server❓
- Forward Proxy🔍
- Reverse Proxy🔍

<br>

<br>

## Proxy Server❓

> 프록시 서버(Proxy Server)는 클라이언트가 자신을 통해서 다른 네트워크 서비스에 간접적으로 접속할 수 있게 해주는 컴퓨터 시스템이나 응용 프로그램을 가리킨다. 서버와 클라이언트 사이에 중계기로서 대리로 통신을 수행하는 것을 가리켜 '프록시', 그 중계 기능을 하는 것을 프록시 서버라고 부른다.

- 인터넷에서 유저를 대신해서 가져오는 서버
  - 클라이언트와 서버 사이의 통신에 중계 역할
  - 클라이언트 - 프록시 서버 - 서버 의 구조를 지님

![img](https://upload.wikimedia.org/wikipedia/commons/thumb/2/27/Open_proxy_h2g2bob.svg/350px-Open_proxy_h2g2bob.svg.png)

- 프록시 서버 중 일부는 서버에 요청된 내용들을 `캐시`를 이용하여 저장
  - 캐시 안의 정보를 요청하는 경우, 바로 정보를 제공함으로써 시간 절약
- 외부와의 트래픽을 줄이게 됨으로써 네트워크 병목 현상 방지

- 프록시 서버를 활용함으로써, 클라이언트 또는 서버의 정보를 숨길 수 있음

<br>

<br>

## Forward Proxy🔍

> 클라이언트가 인터넷에 직접 접근하는 것이 아닌, Forward Proxy Server가 요청을 받고, 인터넷에 연결하여 결과를 다시 클라이언트에 전달해준다.

- 클라이언트가 요청하는 End Point: 실제 서버 도메인
- Forward Proxy에서는 클라이언트의 정보가 감춰짐
  - 요청을 받는 서버는 클라이언트가 누구인지 알 수 없음

![img](https://github.com/ParkJiwoon/PrivateStudy/raw/master/images/forward-proxy.png)



<br>

<br>

## Reverse Proxy🔍

> 클라이언트가 인터넷에 데이터를 요청하면 Reverse Proxy Server가 요청을 받아 내부 서버에서 데이터를 받은 후 클라이언트에 전달

- 클라이언트가 요청하는 End Point: 프록시 서버의 도메인
- Reverse Proxy에서는 서버의 정보가 감춰짐
  - 클라이언트는 실제 서버의 정보를 알 수 없음

![img](https://github.com/ParkJiwoon/PrivateStudy/raw/master/images/reverse-proxy.png)

