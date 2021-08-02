# CSS

### **Cascading Style Sheets**

- 스타일, 레이아웃 등을 통해 문서(HTML)를 표시하는 방법을 지정하는 언어



### CSS 구문

--------

- 선택자(Selector)와 함께 열림
- 선택자를 통해 스타일을 지정할 HTML요소 선택
- 중괄호 안에서 선언 진행

```css
h1{
    color: blue;
    font-size: 15px;
}
```

- 선택자 `h1`
- 선언 `color: blue`
  - `속성: 값`의 쌍
- 속성 `font-size`
- 값 `15px`



### CSS 정의 방법

-------

#### 1. 인라인

- 해당 태그에 직접 `style` 속성 활용

#### 2. 내부 참조(embedding)

- head 태그 내에 `<style>`에 지정

#### 3. 외부 참조(link file)

- 외부 CSS 파일을 `<head>`내 `<link>`를 통해 불러옴







### CSS Selector

------

- 기본 선택자
  - 전체 선택자, 요소 선택자
  - 클래스 선택자, 아이디 선택자, 속성 선택자
- 결합자(Combinators)
  - 자손 결합자(자신보다 아래 전부), 자식 결합자(자신보다 하나 아래)
  - 일반 형제 결합자, 인접 형제 결합자



#### 선택자

- 요소 선택자
  - HTML 태그를 직접 선택
- 클래스 선택자
  - `.`문자로 시작, 해당 클래스가 적용된 모든 항목을 선택
- id 선택자
  - `#`문자로 시작하며, 해당 아이디가 적용된 모든 항목 선택
  - 하나의 문서에 1번만 사용
  - 여러 번 사용해도 동작하지만, 단일id 권장



#### 결합자

- 자손 결합자
  - selectorA 하위의 모든 selectorB
  - `A B`
- 자식 결합자
  - selectorA 바로 아래의 selectorB
  - `A > B`
- 일반 형제 결합자
  - selectorA 형제 요소 중 뒤에 위치하는 selectorB 요소를 모두 선택
  - `A ~ B`
- 인접 형제 결합자
  - selectorA의 형제 요소 중 바로 뒤에 위치하는 selectorB 요소를 선택
  - `A + B`



### CSS 적용 우선순위

----

1. 중요도
   - `!important`
2. 우선 순위
   - 인라인 > id 선택자, 속성 선택자 > class 선택자 > 요소 선택자
3. 소스 순서



### CSS 상속

-----

- 상속을 통해 부모 요소의 속성을 자식에게 상속
- **속성 중에는 상속이 되지 않는 것도 존재**
- 상속되는 것
  - Text 관련 요소, opacity, visibility 등
- 상속 되지 않는 것
  - Box model 관련, position 관련 요소



### CSS 단위

----

#### 크기 단위

- px(픽셀)
  - 모니터 해상도의 한 화소
  - 고정적인 단위
- %
  - 백분율 단위
  - 가변적인 레이아웃에서 활용
- em
  - (바로 위, 부모 요소에 대한) 상속의 영향을 받음
  - 배수 단위, 요소에 지정된 사이즈에 상대적인 사이즈를 가짐
- rem
  - 상속의 영향을 받지 않음
  - 최상위 요소(html)의 사이즈를 기준으로 배수 단위를 가짐

- viewport
  - 웹 페이지를 방문한 유저에게 바로 보이게 되는 웹 컨텐츠의 영역
  - 주로 스마트폰이나 태블릿 디바이스의 화면을 일컫는 용어
  - 디바이스의 viewport를 기준으로 상대적인 사이즈 결정
  - vw, vh, vmin, max



#### 색상 단위

- 색상 키워드
  - 대소문자 구분 X
  - red, blue, black과 같은 특정 색을 직접 글자로 나타냄
- RGB 색상
  - 16진수 표기법 또는 함수형 표기법
  - `#` + 16진수 표기
  - `rgb()`
  - `rgba()` 마지막에 투명도 추가
- HSL 색상
  - 색상, 채도, 명도를 통해 특정 색 표현
  - `hsl()`
  - `hsla()` 마지막에 투명도 추가



#### 문서 표현

- 텍스트
  - 변형 서체
- 컬러, 배경
- 목록 꾸미기
- 표 꾸미기





### CSS Box Model

----

![CSS box-sizing? content-box vs border-box 차이점 정리 | dAsImA](https://dasima.xyz/wp-content/uploads/2019/12/css-box-model-box-sizing.png)

- Margin

  - 테투리 바깥의 외부 여백
  - 배경색을 지정할 수 없음
  - shorthand 존재

  ```
  margin: 10px;
  margin: 10px 20px;
  margin: 10px 20px 30px;
  margin: 10px 20px 30px 40px;
  ```

  - 상하좌우, 상하/좌우, 상/좌우/하, 상/우/하/좌

- Border

  - 테두리 영역
  - shorthand 존재

  ```
  border-width: 2px;
  border-style: dashed;
  border-color: black;
  
  border: 2px dashed black;
  ```

- Padding

  - 테두리 안쪽의 내부 여백
  - 요소에 적용된 배경색, 이미지는 padding까지 적용됨

- Content

  - 글이나 이미지 등 요소의 실제 내용



#### box-sizing

- 기본적으로 `box-sizing`은 `content-box`로 되어있음
  - padding을 제외한 순수 contents 영역
- `box-sizing`을 `border-box`로 하면, border까지의 너비로 설정



#### 마진 상쇄

- 두 블록에 적용된 각각의 margin이 둘 중에서 큰 마진값으로 결합
  - block A의 bottom이 50, block B의 top이 70이라면, 둘 사이는 70





### CSS Display

---

모든 요소는 박스모델이고, 어떻게 보여지는 지에 따라 문서에서의 배치가 달라질 수 있음

HTML 요소들을 시각적으로 어떻게 보여줄지 결정하는 속성

- `display: block`
  - 줄 바꿈이 일어나는 요소
  - 화면 크기 전체의 가로 폭 차지
  - 블록 레벨 요소 안에 인라인 레벨 요소가 들어갈 수 있음
  - div/ ul, ol, li/ p/ hr/ form
- `display: inline`
  - 줄 바꿈이 일어나지 않는 행의 일부 요소
  - content 너비만큼 가로 폭을 차지
  - width, height, margin-top, margin-bottom 지정할 수 없음
  - 상하여백은 line-height
  - span/ a/ img/ input, label/ b, em, i, strong
- `display: inline-block`
  - `block`과 `inline` 레벨 요소의 특징을 모두 가짐
  - `inline`처럼 한 줄에 표시 가능
  - `block`처럼 width, height, margin 속성 지정 가능
- `display: none`
  - 해당 요소를 화면에 표시 X (공간도 사라짐)
  - `visibility: hidden`은 공간은 차지하나 화면에 표시되지 않음





### CSS Position

----

- 문서 상에서 요소를 배치하는 방법 지정
- `static`: 모든 태그의 기본 값(기준 위치)
  - 좌측 상단이 기본 값
  - 부모 요소 내에서 배치될 때는 부모 요소의 위치가 기준
- 좌표 property(`top`, `bottom`, `left`, `right`)를 사용하여 이동 가능
  - `relative` 상대 위치
    - 자기 자신의 static 위치를 기준으로 이동
    - 레이아웃에서 요소가 차지하는 공간은 static일 때와 같음
  - `absolute` 절대 위치
    - 요소를 일반적인 문서 흐름에서 제거 후 레이아웃에 공간 차지 X
    - static이 아닌 가장 가까이 있는 부모/조상 요소를 기준으로 이동(없는 경우 body에 붙음)
  - `fixed` 고정 위치
    - 요소를 일반적인 문서 흐름에서 제거 후 레이아웃에 공간 차지 X
    - 부모 요소와 관계 없이 viewport를 기준으로 이동
    - 항상 같은 곳에 위치

