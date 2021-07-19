## 📌연산자

#### 산술 연산자

- `+` 덧셈
- `-` 뺄셈
- `*` 곱셈
- `/` 나눗셈
  - 나눗셈은 항상 결과가 float
- `//` 몫
- `%` 나머지
- `**` 거듭제곱



#### 비교 연산자

- 값을 비교, Boolean 값 리턴(True, False)
- `<`, `<=`, `>`, `>=`, `==`, `!=`
- `is`, `is not`: 객체 아이덴티티 판단
  - 특정 변수가 비어있는 지 확인할 때는 `is None` 사용 권장



#### 논리연산자

- A and B: A와 B 모두 True인 경우, True 리턴
- A or B :A와 B중 하나라도 True인 경우, True 리턴
- Not: True는 False 리턴, False는 True 리턴

- **결과가 확실한 경우 두 번째 값은 확인하지 않고 첫 번째 값 반환**
  - and 연산에서 첫 번째 값이 False인 경우: 첫 번째 값 반환
  - or 연산에서 첫 번째 값이 True인 경우: 첫 번째 값 반환

```python
a = 9 and 3
b = 3 or 5
c = 0 and 5
d = 8 or 0
print(a)
print(b)
print(c)
print(d)
```

```
3
3
0
8
```

#### 복합 연산자

- 연산과 대입이 함께 이루어지는 경우

  - `+=`, `-=`, `*=` 등

  ```python
  a = 10
  a = a + 1
  print(a)
  b = 10
  b += 1
  print(b)
  ```

  ```
  11
  11
  ```

  









#### 📌Indexing, Slicing

- `[]`를 통해 값에 접근하고, `:` 를 통해 슬라이싱을 할 수 있음

```python
s = 'hello'
print(s[0])
print(s[1:3])
```

```
'h'
'el'
```

- 슬라이싱을 할 때, `1:3`의 경우 3번째 인덱스는 포함 X