### Node.js 모듈 사용법

- Node.js에서는 모듈을 불러오기 위해 `require` 활용
  - `require` 함수는 `module.exports`를 return

```javascript
var require = function(src){                 //line 1
    var fileAsStr = readFile(src)            //line 2
    var module.exports = {}                  //line 3
    eval(fileAsStr)                          //line 4
    return module.exports                    //line 5
}
```

1. `src` 파일을 받아온다.
2. `src` 파일을 읽어 `fileAsStr`에 저장한다.
3. `module.exports`를 빈 객체로 초기화
4. `fileAsStr`을 실행
5. `module.exports`를 return

- 같은 디렉토리의 `circle.js`을 import 하는 경우
  - 모듈 확장자는 생략 가능

```javascript
//circle.js
const {PI} = Math; //3.1415926535 8979323846 2643383279...

exports.area = (r) => PI * r * r;

exports.circumference = (r) => 2 * PI * r;
```

```javascript
const circle = require('./circle.js'); // == require('./circle')

console.log(`지름이 4인 원의 면적: ${circle.area(4)}`);
console.log(`지름이 4인 원의 둘레: ${circle.circumference(4)}`);
```

- `require` 의 함수의 인수에는 파일 뿐만 아니라 디렉토리도 지정 가능
  - 모듈을 명시하지 않고 `require` 함수를 호출하면 해당 디렉토리의 `index.js` 로드

<br>

### exports & module.exports

- `exports`는 `module.exports`의 alias지만, `exports` 객체에는 값을 할당할 수 없음

| 구분           | 모듈 정의 방식                                               | require 함수 호출 결과                                       |
| -------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| exports        | `exports` 객체에는 값을 할당할 수 없고, <br />공개할 대상을 `exports` 객체에 프로퍼티 또는 메소드로 추가 | `exports` 객체에 추가한 프로퍼티와 메소드가 담긴 객체가 전달 |
| module.exports | `module.exports` 객체에 **하나의 값**(원시 타입, 함수, 객체)만을 할당한다. | `module.exports` 객체에 할당한 값이 전달                     |

- `module.exports`에는 1개의 값만 할당할 수 있다고 했지만, 객체를 사용하여 여러 기능을 하나로 묶는 방식을 활용할 수 있다.

```javascript
// foo.js
module.exports = {
  add (v1, v2) { return v1 + v2 },
  minus (v1, v2) { return v1 - v2 }
};
```

```javascript
// app.js
const calc = require('./foo');

const result1 = calc.add(1, 2);
console.log(result1); // => 3

const result2 = calc.minus(1, 2);
console.log(result2); // => -1
```

