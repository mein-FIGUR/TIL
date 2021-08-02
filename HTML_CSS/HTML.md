# HTML

**Hyper Text Markup Language**

- Hyper
  - 텍스트 등의 정보가 다중으로 연결된 상태

- Hyper Text
  - 참조를 통해 다른 문서로 접글할 수 있는 텍스트
  - 쓰인 기술들 중 가장 중요한 2가지 **http**, **html**
- Markup Language
  - 태그 드을 활용, 문서나 데이터의 구조를 명시하는 언어
  - 데이터를 표현하기만 함(프로그래밍 언어와 다름)
  - **HTML**, **Markdown**
- 웹 컨텐츠의 의미와 구조를 정의





## HTML 기본 구조

- DOM(Document Object Model) 트리 구조
  - 문서의 구조화된 표현 제공 
  - 프로그래밍 언어가 DOM 구조에 접근할 수 있는 방법 제공

![문서 객체 모델 - 위키백과, 우리 모두의 백과사전](https://upload.wikimedia.org/wikipedia/commons/thumb/5/5a/DOM-model.svg/1200px-DOM-model.svg.png)



```html
<!DOCTYPE html>
<html>
    <head>
        
    </head>
    <body>
        
    </body>
</html>
```

- head, body로 구성
- 큰 태그일수록 왼쪽에 있고, 자식 태그일수록 들여쓰기(`2 spaces` or 4 spaces)로 구조화



#### HEAD

- 문서 제목, 문자코드와 같이 해당 문서 정보를 담고 있음
- 브라우저에서는 나타나지 않음
- Open Graph Protocol: 메타 데이터를 표현하는 새로운 규약

#### BODY

- 브라우저 화면에 나타나는 정보
- 실제 내용



#### ELEMENT

- HTML 요소는 태그와 내용(contents)로 구성
  - 태그가 내용을 감싸는 구조
  - 태그가 정보의 성격와 의미를 나타냄
- 항상 쌍이 잘 맞는지 확인

```html
<h1>
    contents
</h1>
```

- 내용이 없는 태그
  - br, hr, img, input, link, meta
- 요소는 중첩될 수 있음
  - 요소의 중첩을 통해 하나의 문서 구조화



#### Attribute

- 태그 안에 활용할 수 있는 속성 이름과 값
  - 부가적인 정보 설정
  - 시작 태그에 작성
  - 보통 이름과 같이 하나의 쌍으로 존재
- 태그별로 사용 가능한 속성이 다름
  - 태그와 상관없이 사용 가능한 속성도 존재
    - `HTML Global Attribute`
    - id, class, hidden, lang, style, tabindex, title
    - 몇몇 요소에는 효과가 없을 수 있음
- 공백 없이, 쌍따옴표`""` 사용

```html
<a href="https://google.com"></a>
```





### 시맨틱 태그

- 의미론적 요소를 담은 태그 ~~div~~
  - 구역을 나누는 것 뿐 아니라 의미를 가지는 태그를 활용하기 위한 노력
  - Non semantic 요소 `div`, `span`
- `header`: 문서 전체나 섹션의 머릿말 부분
- `nav`: 네비게이션
- `aside`: 메인 콘텐츠와 관련이 적은 콘텐츠
- `section`: 문서의 일반적인 부분, 컨텐츠의 그룹 표현
- `article`: 문서, 페이지, 사이트 안에서 독립적으로 구분
- `footer`: 문서 전체나 섹션의 마지막 부분





## HTML 문서 구조화

- 그룹 컨텐츠
  - `<p>`
  - `<hr`>
  - `<ol>`, `<ul>`
  - `<pre>`, `<blockquote>`
  - `<div>`
- 텍스트 관련
  - `<a>`
  - `<b>`, `<strong>`
    - `<b>`는 굵게, `<strong>`은 강조
  - `<i>`, `<em>`
  - `<span>`, `<br>`, `<img>`

- table
  - `<tr>`, `<td>`, `<th>`
  - `<thead>`, `<tbody>`, `<tfoot>`
  - `<caption>`
  - `<colspan>`, `<rowspan>`
    - 셀 병합
  - `<col>`, `<colgroup>`
- form
  - `<form>`
  - 서버에서 처리될 데이터를 제공
  - 기본 속성 action, method
    - action: 어디로 보낼 지
    - method: http method
- input
  - 다양한 타입을 가지는 입력 데이터 필드
  - form안에 들어감
  - type에 따라 요소의 동작이 달라짐
  - 공통 속성
    - name, placeholder
    - required
    - autofocus