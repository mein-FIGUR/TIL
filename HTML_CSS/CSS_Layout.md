# CSS Layout

- Display
- Position
- Float
- Flexbox
- Grid system



## Float

- 본래는 이미지를 한쪽에 띄우고 텍스트를 둘러싸는 레이아웃을 위해 도입
- 현재는 이미지가 아닌 다른 요소들에도 적용해 웹 사이트의 전체 레이아웃을 만드는데까지 발전
- 한 요소가 정상 흐름으로부터 빠져 텍스트 및 인라인 요소가 그 주위를 감싸 요소의 좌, 우측을 따라 배치되어야 함을 지정
- flexbox, grid 레이아웃과 같은 기술이 나오기 전에 열 레이아웃을 만드는데 활용
  - flexbox, grid의 출현으로 float는 이미지를 위한 역할로 돌아감



#### 속성

- none: 기본값
- left: 요소를 왼쪽으로 띄움
- right: 요소를 오른쪽으로 띄움



#### Float clear

- float된 요소의 부모 요소에 작성

- `class="clearfix"`: 관행적으로 `clearfix` 라는 클래스 이름을 사용
- `.clearfix::after`: `clearfix` 뒤에 생성
  - `::after` 선택한 요소의 맨 마지막 자식으로 가상 요소(의사 요소)를 하나 생성, 기본값은 인라인

```css
.clearfix::after {
      content: "";
      display: block;
      clear: both;
}
```





## Flexbox

- float와 positioning은 제한적이고 한계가 있음
- 요소 간 공간 배분과 정렬 기능을 위한 1차원(단방향) 레이아웃
- 요소
  - Flex Container (부모 요소)
  - Flex item (자식 요소)
- 축
  - main axis (메인 축)
  - cross axis (교차 축)



#### 구성 요소

- Flex Container
  - Flexbox 레이아웃을 형성하는 가장 기본적인 모델
  - Flex Item들이 놓여있는 영역
  - 생성하려면 display 속성을 flex 혹은 inline-flex로 지정
- Flex Item
  - 컨테이너의 컨텐츠



#### 속성

- 배치 방향 설정(메인축)
  - `flex-direction`
  - 단방향 레이아웃이기 때문에, 메인축 방향만 바뀜
- 메인축 방향 정렬
  - `justify-content`
- 교차축 방향 정렬
  - `align-items`, `align-self`, `align-content`
- 기타
  - `flex-wrap`, `flex-flow`, `flex-grow`, `order`



#### content & items & self

- content: 여러 줄
- items: 한 줄
- self: flex item 개별 요소



### 정리

- `display: flex`
  - **정렬하려는 부모 요소에 작성**
  - `inline-flex`: flex 영역을 블록으로 쓰지 않고 인라인 블록으로 사용
- `flex-direction`
  - **item이 쌓이는 방향 설정**
  - **main-axis가 변경**
  - `row`(기본값): 주축의 방향이 왼쪽에서 오른쪽
  - `row-reverse`: 주축의 방향이 오른쪽에서 왼쪽
  - `column`: 주축의 방향이 위에서 아래
  - `column-reverse`: 주축의 방향이 아래에서 위
- `flex-wrap`
  - **요소들이 강제로 한 줄에 배치되게  할 것인지 여부**
  - `nowrap`(기본값): 모든 아이템들을 한 줄에 나타내려고 함, 범위를 벗어날 수 있음
  - `wrap`: 넘치면 다음줄로 넘어감
  - `wrap-reverse`: 넘치면 윗줄로 넘어감
- `flex-flow`
  - `flex-direction`과 `flex-wrap`의 shorthand
  - `flex-direction`과 `flex-wrap`에 대한 설정 값을 차례로 작성
- `justify-content`
  - main-axis 정렬
  - `flex-start`(기본값): 시작 지점부터 차례로
  - `flex-end`: 뒤쪽에서부터 쌓임(역순 X)
  - `center`: 중앙
  - `space-between`: 좌우 정렬(item들 간의 간격이 동일)
  - `space-around`: 균등 좌우 정렬(내부 요소 여백은 외곽 여백의 2배)
  - `space-evenly`: 균등 정렬(모든 여백 동일)
- `align-items`
  - cross-axis 정렬
  - `stretch`(기본값): 컨테이너 가득 채움
  - `flex-start`: 위
  - `flex-end`: 아래
  - `center`: 가운데
  - `baseline`: item 내부의 text에 기준선 맞춤
- `align-self`
  - 개별 item에 적용하는 속성
  - `auto`(기본값)
  - `flex-start`
  - `flex-end`
  - `center`
  - `baseline`
  - `stretch`: 부모 컨테이너에 자동으로 맞춰서 늘어남
- `order`
  - 작은 숫자일 수록 앞(우선 쌓이는 방향)으로 이동
  - 기본 값 0
  - 음수도 가능
- `flex-grow`
  - 주축에서 남는 공간을 항목들에게 분배하는 방법
  - 각 아이템의 상대적 비율을 정하는 것은 아님
  - 기본 값 0
  - 음수 불가능