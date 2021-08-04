# Bootstrap

> The most popular HTML, CSS, and JS library in the world

- 트위터에서 시작된 오픈 소스 프론트엔트 라이브러리
- 웹 페이지에서 많이 쓰이는 요소 거의 전부를 내장
- 별도의 디자인을 할 시간이 크게 줄어들고, 여러 웹 브라우저를 지원하기 위한 크로스 브라우징에 불필요한 시간을 사용하지 않도록 함
- 하나의 코드로 여러 사용을 할 수 있음(one source multi use)





### CDN

- Content Delivery(Distribution) Network
- 컨텐츠를 효율적으로 전달하기 위해, 서버와 사용자 사이의 물리적 거리를 줄여 컨텐츠 로드 지연을 최소화
- 분산된 서버로 이루어진 플랫폼
  - 전 세계 사용자들이 로딩 시간을 늦추지 않고 동일한 품질의 컨텐츠 사용 가능
- 사용자와 가까운 서버를 통해 빠르게 전달 가능
- 외부 서버를 활용함으로써 본인 서버의 부하가 적어짐





### Grid System

- flexbox로 제작됨
- `container`, `rows`, `column`으로 컨텐츠 배치하고 정렬
  - 12개의 column, 6개의 grid breakpoints

- `row`
  - columns 의 wrapper
- gutters
  - grid 시스템에서 반응적으로 공간을 확보하고 컨텐츠를 정렬하는 데 사용되는 column 사이의 padding
- `col`, `col-*`
  - row당 가능한 12개 중 사용하려는 columns 수를 나타냄
  - 너비는 백분율로 설정되어 부모 요소를 기준으로 유동적으로 크기가 조정
  - grid layout에서 내용은 반드시 columns 안에 있어야 하며 오직 columns만 row의 바로 하위 자식일 수 있음



### Grid breakpoints

- 다양한 디바이스에서 적용하기 위해 특정 픽셀 조건에 대한 지점을 정해둠
- bootstrap은 대부분의 크기를 정의하기 위해 em 또는 rem 사용
  - px은 grid breakpoint에 사용
  - viewport 너비가 픽셀단위이고 글꼴 크기에 따라 변하지 않기 떄문

