# String

- 문자들의 나열
- Immutable
- Ordered
- Iterable





### String Method

- `.find(x)`
  - 문자열 조회/탐색
  - `x`의 첫 번째 위치를 반환, 없으면 -1 반환

```python
'water'.find('b') # -1
'useless'.find('s') # 1
```

- `.index(x)`
  - `x`의 첫 번째 위치를 반환, 없으면 오류 발생

```python
'useless'.index('s') # 1
'useless'.index('a') #ValueError
```

- `.replace(old, new[, count])`
  - `old`를 `new`로 바꿔서 반환
  - `count`를 지정하면 해당 개수만큼 시행

```python
'useless'.replace('s', 'a') #uaeleaa
'useless'.replace('s', 'a', 2) #uaeleas
```

- `.strip([chars])`
  - 특정 문자`chars` 지정하면, 메소드에 따라 해당 방향에서 제거
  - 문자열 지정하지 않으면 공백 제거
  - `.strip()` 양쪽, `.lstrip()` 왼쪽, `.rstrip()` 오른쪽

```python
'  hello  '.strip() #hello
'  hello  '.rstrip() #  hello
'  hello  '.lstrip() #hello  
```

- `.split([chars])`
  - 문자열을 특정한 단위로 나눠 리스트로 반환

```python
'a b c'.split() #['a', 'b', 'c']
```

- `'seperator'.join([iterable])`
  - `iterable` 컨테이너 요소들을 `seperator`로 합쳐 문자열 반환

```python
"-".join(['a', 'b', 'c']) #'a-b-c'
```

- `.capitalize()` 첫 글자를 대문자, 나머지 소문자

```python
'heLLo'.capitalize() #Hello
```

- `.title()` `'` 또는 공백 이후의 첫 문자를 대문자

```python
"heLLo, it's mE".title() #"Hello, It'S Me"
```

- `.upper()` 모두 대문자
- `.lower()` 모두 소문자
- `.swapcase()` 대문자 <-> 소문자 변경
- `.isalpha()` 알파벳 문자 여부
  - 유니코드 기준이므로, 한글도 True를 반환
- `.isupper()` 대문자 여부
- `.islower()` 소문자 여부
- `.istitle()` 타이틀 형식여부
- `.isdecimal()`, `.isdigit()`, `.isnumeric()` 
  - 숫자 여부, 상황에 따라 판단하는 것이 다름





















