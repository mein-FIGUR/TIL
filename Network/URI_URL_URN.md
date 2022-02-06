# URI & URL & URN

<br>

## URI(Uniform Resource Identifier)

- 통합 자원 식별자
- 위치나 이름, 또는 둘 다를 기준으로 자원을 식별한다.
- URI에는 URL, URN이 존재한다.(URI의 하위 개념이 URL, URN)
    - URN과 URL은 모두 URI이며, 특정 URI는 URL이자 URN이 될 수 있다.
    - URL는 URI이다.
    - URI가 반드시 URL일 필요는 없다.

<br>

## URL(Uniform Resource Locator)

- 식별된 자원을 사용할 수 있는 위치와 이를 검색하는 매커니즘을 지정하는 URI의 하위 집합
- 자원을 얻을 수 있는 방법을 정의
- 식별된 자원의 가용성을 의미하지 않는다.

![](https://media.vlpt.us/images/shleecloud/post/27525e87-d8a9-486a-ac24-99bbe2764cfc/uri.png)

- protocol(scheme): 통신 프로토콜
- host: 웹 페이지, 이미지, 동영상 등의 파일이 위치한 웹 서버, 도메인 또는 IP
- port: 웹 서버에 접속하기 위한 통로
- path: 웹 서버의 루트 디렉토리로부터 웹 페이지, 이미지, 동영상 등의 파일 위치까지의 경로
- query string: 웹 서버에 전달하는 추가 질문

<br>

## URN(Uniform Resource Name)

- 리소스를 영구적이고 유일하게 식별할 수 있는 URI
- URN 체계를 사용하는 URI
- URN이 “what”을 의미한다면, URL은 “where”를 의미한다.
- `urn : '이름공간식별자' : '이름공간에 대한 특별 문자열'` 과 같은 형태로 구성된다.

<br>

```
URL: ftp://ftp.is.co.za/rfc/rfc1808.txt
URL: http://www.ietf.org/rfc/rfc2396.txt
URL: ldap://[2001:db8::7]/c=GB?objectClass?one
URL: mailto:John.Doe@example.com
URL: news:comp.infosystems.www.servers.unix
URL: telnet://192.0.2.16:80/
URN (not URL): urn:oasis:names:specification:docbook:dtd:xml:4.1.2
URN (not URL): tel:+1-816-555-1212 (disputed, see comments)
```