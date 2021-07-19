### 📌Python 특징

- 인터프리터 언어(Interpreter)
  - 소스 코드를 컴파일하지 않고, 한 줄씩 소스코드를 읽어서 바로 실행
  - 컴파일 언어(C언어, 자바 등)에 비해 느릴 수 있지만 빌드 과정이 없어 바로 실행 가능
  - 컴파일 언어(번역) vs 인터프리터 언어(통역)
    - 실행 속도: 컴파일 언어 > 인터프리터 언어
    - 개발 난이도: 컴파일 언어 < 인터프리터 언어
- 객체 지향 프로그래밍(Object Oriented Programming)
  - 파이썬은 모두 객체로 이루어져 있음
- 동적 타이핑(Dynamic Typing)
  - 변수에 별도의 타입 지정이 필요 없음
  - Javascript도 동적 타이핑 언어



### 📌Python 개발 환경

- 대화형 환경
  - Python 기본 Interpreter(IDLE)
  - Python Jupyer Notebook
  - Google colab (데이터 사이언스에서 많이 쓰임)
- 스크립트 실행
  - .py 파일 작성 후 IDE(Pycharm) 혹은 Text Editor(VS Code) 활용



### 📌코드 작성 가이드

- 코드를 '어떻게 작성할지'에 대한 가이드라인
  - PEP8 <https://www.python.org/dev/peps/pep-0008/> : 파이썬에서 제안하는 스타일 가이드
  - Google Style guide <https://google.github.io/styleguide/pyguide.html> 등 기업, 오픈소스 등에서 사용되는 스타일 가이드
- 1줄에 1문장(statement)이 원칙
- 문장(statement)은 파이썬이 실행 가능한 최소한의 코드 단위
  - 파이썬에서는 세미콜론 작성 X
  - 1줄로 표기할 때는 세미콜론`;` 을 작성하여 표기할 수 있음



### 📌주석

- 한 줄 주석은 `#`으로 표현
- 여러 줄의 주석은 한 줄씩 `#`을 사용하거나, `"""` 또는 `'''` 으로 표현
  -  `"""` 또는 `'''`  은 docstring을 위해 사용한다
  - 한 번에 주석 넣기 `ctrl + /`
- 특수한 형태의 주석: docstring
  - 함수/클래스의 설명 작성