# Nginx

<br>

- Nginx❓





<br>

## Nginx❓

> Nginx는 웹 서버 소프트웨어로, 가벼움과 높은 성능을 목표로 한다. 웹 서버, 리버스 프록시 및 메일 프록시 기능을 가진다. 요청에 응답하기 위해 비동기 이벤트 기반 구조를 가진다는 점이 Apache HTTP 서버의 쓰레드/프로세스 기반 구조를 가지는 것과 대조적이다.

- 경량 웹 서버
- 정적 파일을 응답해주는 HTTP Web Server의 기능
- **Reverse Proxy Server**로 활용하여 WAS 서버의 부하를 줄일 수 있는 로드 밸런서로 활용되기도 함
- **Event-Driven**구조를 지니고 있다는 점이 가장 큰 특징

<br>

## Apache vs Nginx

- Apache
  - 쓰레드/프로세스 기반 구조로 요청 하나당 쓰레드 하나가 처리하는 구조
  - 사용자가 많으면 많은 쓰레드 생성, 메모리 및 CPU 낭비가 심함
- Nginx
  - 비동기 Event-Driven 기반 구조
  - 다수의 연결을 효과적으로 처리
  - 대부분의 코어 모듈이 Apache보다 적은 리소스로 더 빠르게 동작
  - 더 작은 쓰레드로 클라이언트의 요청들을 처리

<br>

## Nginx의 구조

- 하나의 Master Process와 다수의 Worker Process로 구성
- Master Process
  - 설정 파일을 읽고, 유효성 검사 및 Worker Process 관리
- Worker Process
  - 요청 처리