## 📌Container

- 여러 개의 값을 저장할 수 있는 객체
- sequence형: 순서가 있는(ordered) 데이터
  - 인덱스를 활용해 접근 가능
  - 순서가 있는 것과 정렬되어 있는 것은 다름
  - list, tuple, range, string, binary
- non-sequence형: 순서가 없는(unordered) 데이터
  - set, dictionary



## 📌Sequence

### 모든 Sequence형에서 활용할 수 있는 연산자

- Indexing: 인덱스를 활용해 접근 가능 `[]` 
- Concatenation: sequence형을 합칠 수 있음 `+` (range는 예외)
- Repetition: sequence형을 여러개 concatenate 가능 `*` (range는 예외)
- Membership: sequence 안에 item이 있는 지 확인 `in`
- Length: sequence안의 item의 개수 `len`
- Slicing: sequence의 일부를 뽑아낼 수 있음 `[ : ]`
- Max, Min: sequence안의 최대값, 혹은 최소값 `max()`, `min()`



### 📌list

- `[]` 또는 `list()` 를 통해 생성
- 인덱스를 활용해 리스트 내의 값에 접근 가능
  - 처음 값 `[0]`, 마지막 값 `[-1]`
- Mutable: 각각의 원소는 값이 바뀔 수 있음
- 리스트를 복사할 때, `b = a`의 꼴로 복사하면 안됨
  - `b = list(a)` 또는 `b = a[:]` 꼴로 복사해야 함
  - `b = a`는 같은 주소값을 가리키게 되어있음



### list Method

리스트 `a` 가 있다고 가정

- `a.append(item)`: 리스트의 끝에 item 추가
- `a.insert(i, item)`: i번째 인덱스에 item 삽입(i 이후의 것들은 뒤로 한 칸씩 인덱스 밀림)
- `a.pop()`: 마지막 인덱스에 위치한 값 없애고 리턴
  - `a.pop(i)`: i번째 인덱스에 위치한 값 없애고 리턴
- `a.sort()`: 리스트 정렬
  - `a.reverse()`: 리스트 역순 정렬
- `del a[i]`: i번째 인덱스에 있는 값 제거
- `a.index(item)`: item이 위치한 인덱스 값 리턴
- `a.count(item)`: 리스트 안의 item 개수 리턴
- `a.remove(item)`: 가장 먼저 나타나는 item 제거



### 📌tuple

- `()` 또는 `tuple()` 을 통해 생성
- 인덱스를 활용해 튜플 내의 값에 접근 가능
- Immutable: 수정이 불가능함
- **하나의 항목으로 구성된 튜플**은 값 뒤에 쉼표 필요 `(1, )`



### 📌range

- 숫자의 시퀀스
- Immutable
- `range(n)` : 0부터 n-1까지 숫자들
- `range(a, b)` : a부터 b-1까지 숫자들
- `range(a, b, gap)` : a부터 b-1까지 gap만큼 증가시킨 숫자들
- 담겨 있는 숫자를 확인하고자 한다면, list로 type casting 하여 확인 가능



### 📌string

- Immutable
- 문자의 시퀀스



### string Method

문자열 `text`가 있다고 가정

- `text.split()`: 문자열을 띄어쓰기를 기준으로 분리
  - `text.split(",")`: `,`를 기준으로 문자열 분리
  - 리스트의 경우, `''.join(word)`와 같은 식으로 하나의 string으로 변환 가능
- `text.upper()`: 문자열 내 알파벳을 대문자로 치환
- `text.lower()`: 문자열 내 알파벳을 소문자로 치환
- `text.center(w)`: 문자열을 길이 w로 설정하고, 가운데에 값을 둠
- `text.rjust(w)`: 문자열을 우측정렬하고, 길이를 w로 맞춤
- `text.ljust(w)`: 문자열을 좌측정렬하고, 길이를 w로 맞춤
- `text.count(item)`: 문자열 내 item의 갯수를 리턴
- `text.find(item)`: 문자열 내 item이 처음으로 나타나는 인덱스 값 리턴

