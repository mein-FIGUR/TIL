## 📌Non-Sequence



### 📌Dictionary

- key, value 쌍으로 이루어진 구조
- `{}` 또는 `dict()` 통해 생성
- key를 통해 value에 접근
- key는 immutable, value는 mutable
  - key는 str, int, float, boolean, tuple, range만 가능
  - value는 모든 값으로 설정 가능



### Dictionary Method

딕셔너리 `d`가 있다고 가정

- `d.keys()`: 딕셔너리의 key값들만 리스트로 리턴
- `d.values()`: 딕셔너리의 value값들만 리스트로 리턴
- `d.items()`: 딕셔너리에서 `(key, value)` 의 튜플 형태로 이루어진 리스트 리턴
- `d.get(key)`: 해당 key값의 value값 리턴
- `del d[key]`: 딕셔너리에서 key, value 동시에 제거
- `key in d` : 딕셔너리 안에 key가 존재하는 지 확인





### 📌Set

- `{}` 또는 `set()`을 통해 생성
  - 빈 set를 만들기 위해서는 set()을 활용해야 함
- 수학에서 집합과 동일한 구조를 가짐
  - 집합 연산 가능, 중복된 값 존재 X



### Set Method

set `set1`, `set2`가 있다고 가정

- `item in set1`: 세트에 값이 있는 지 확인
- `len(set1)`: 세트의 개수 리턴
- `set1 | set2 `, `set1.union(set2)`: 두 세트의 합집합
- `set1 & set2`, `set1.intersection(set2)`: 두 세트의 교집합
- `set1 - set2`, `set1.difference(set2)`: set1에서 set2를 뺀 차집합
- `set1 <= set2`, `set1.issubset(set2)`: set2에 set1의 원소가 전부 들어있는 지 확인 
  - 왼쪽 화살표로만 사용 가능
- `set1.add(item)`: set에 item 추가
- `set1.remove(item)`: set에 item 제거
- `set1.pop()`:set에서 임의로 원소 하나 제거
- `set1.clear()`: set에서 모든 원소 제거



### 📌frozenset

- `frozenset()`을 통해 생성
- 한 번 객체를 만들면 변경할 수 없음
- `set`과 연산 가능
  - `set | frozenset` , `frozenset | set`처럼 순서에 따라 나오는 결과의 타입이 달라짐
    - 앞의 자료형 기준