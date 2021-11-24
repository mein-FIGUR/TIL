## Puppeteer

- 공식홈페이지 : <https://github.com/puppeteer/puppeteer>
- Chrome 또는 Chromium을 [DevTools Protocol](https://chromedevtools.github.io/devtools-protocol/)로 제어하는 Node.js 라이브러리, 헤드리스 크롬을 기본적으로 지원하며 구글 크롬 개발팀이 직접 만든 라이브러리이다.
- Chrome 59부터 Headless 지원
- Puppeteer는 Node 6 이상에서 동작

<br>

#### Puppeteer 설치

```
npm i puppeteer
```

- 최신 버전의 Chromium 포함

```
npm i puppeteer-core
```

- 브라우저를 다운받는 과정을 포함하지 않은 패키지

<br>

### Puppeteer 기능

- Chrome Extensions 테스트
- SPA(Single-Page Application) 크롤링
- 미리 렌더링 된 컨텐츠(SSR, Server Side Rendering) 생성
- 렌더링 후 키보드, 마우스 입력 제어
- 웹 페이지의 자동 테스트 도구 
- 접속한 페이지의 스크린샷이나 PDF파일 생성 가능

<br>

### Headless Browser

- CLI(Command Line Interface)에서 작동하는 브라우저
- 만든 화면을 사용자에게 보여주지 않지만, 일반적인 브라우저처럼 웹페이지에 접속하여 DOM Tree와 CSSOM Tree를 만들고, JS엔진을 구동한다.
- 백그라운드에서 동작

<br>

### Puppeteer 구조

- 계층적
- Puppeteer는 하나의 Browser를 갖는다.
- 하나의 Browser는 여러 BrowserContext를 가질 수 있다.
- 하나의 BrowserContext는 여러 Page를 가질 수 있고, Serviceworker와 Session을 가질 수 있다.
- 하나의 Page는 여러 Frame을 가질 수 있다.
- 하나의 Frame은 여러 Context를 가질 수 있다.

![Headless browser - Puppeteer](https://datacadamia.com/_media/web/browser/puppeteer_architecture.png?w=400&h=391&buster=1588756015&tok=484de4)

<br>

### Tips

#### Page

- `Page` 클래스는 `EventEmitter` 클래스를 상속받는다.
  - `EventEmitter`의 `on` 메소드는 이벤트의 타입과 리스너를 인자로 받아 `Emitter` 객체에 추가하는 역할
  - `on` 함수는 특정 상황에 실행시킬 리스너 함수를 `Emitter`안에 등록한다는 의미를 갖고 있음

```javascript
function Emitter() {
  this.events = {};
}

Emitter.prototype.on = function(type, listener) {
  this.events[type] = this.events[type] || [];
  this.events[type].push(listener);
}
```

- `screenshot`
  - 해당 url의 스크린샷을 찍는다.
  - `fullPage`를 true로 설정하면 전체 페이지의 스크린샷을 찍는다.
- `$()`
  - `page` 안에서 `document.querySelector`역할을 한다.
  - 일치하는 셀렉터가 없다면, `null` 반환
- `$$()`
  - `page` 안에서 `document.querySelectorAll` 역할을 한다.
  - 일치하는 셀렉터가 없다면, `[]` 반환
- `$eval(selector, pageFunction)`
  - `document.querySelector`을 적용한 값을 `pageFunction`의 첫번째 argument로 넣는다.
  - 일치하는 셀렉터가 없다면 에러 발생
- `$$eval(selector, pageFunction)`
  - `document.querySelectorAll`을 적용한 값을 `pageFunction`의 첫번째 argument로 넣는다.
- `evaluate(pageFunction[, ...args])`
  - `args`에는 `pageFunction`에 넣을 argument들이 들어간다.
  - `pageFunction`에서 리턴된 value

```javascript
const result = await page.evaluate((x) => {
  return Promise.resolve(8 * x);
}, 7);
console.log(result); // prints "56"
```

#### event: 'dialog'

- `dialog`가 나타났을 때 보여지는 이벤트
  - `dialog`는 `alert`, `prompt`, `confirm`, `beforeunload`를 말함

### Element

- `Document`안의 모든 객체가 상속하는 제일 범용적인 기반 클래스
- `page`에서 `$` 와 같은 방식으로 `element`를 얻을 수 있다.
- `textContent`
- `getAttribute()`

