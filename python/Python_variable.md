### 📌변수

- `type()` 을 통해 변수에 할당된 값의 타입 확인 가능
- `id()` 를 통해 변수에 할당된 값의 고유한 아이덴티티 값인 메모리 주소 확인 가능
- `=` 연산자(할당 연산자)를 통해 값을 할당(assignment)
  - `=` 를 통해 같은 값을 동시에 할당 가능
  - 다른 값을 동시에 할당 가능(multiple assignment)

```python
a, b = 2, 3
print(x,y)
```

```
2 3
```



- multiple assignment를 통해서 값을 바꾸는 것도 가능(Pythonic한 방법)

```python
x, y = 1, 2
x, y = y, x
print(x, y)
```

```
2 1
```



### 📌식별자

- 변수, 함수, 모듈, 클래스 등을 실별하는 데 사용하는 이름

- 규칙

  - 이름은 영문 알파벳, 언더스코어`_`, 숫자로 구성

  - 첫 글자에 숫자가 올 수 없음

  - 길이 제한 X, 대소문자 구별

  - 내장 함수, 모듈 등의 이름으로 만들면 안됨

    - 원래 기능이 동작하지 못함

  - 몇몇 키워드는 사용할 수 없음(Ture, False, break, while 등)

    - 키워드 확인 방법

    ```python
    import keyword
    print(keyword.kwlist)
    ```

    

### 📌데이터 타입

- 숫자(Number)
  - int(정수)
  - float(부동소수점, 실수)
  - complex(복수)
- 문자열(String)
- 참/거짓(Boolean)
- None



#### int

- 모든 정수의 타입
  - Python 2까지는 long이 있었으나, Python 3부터는 모두 int로 표기
- 매우 큰 수를 나타내도 overflow 발생 X
- 진수 표현도 가능
  - 2진수 `0b`
  - 8진수 `0o`
  - 16진수 `0x`



#### float

- 정수가 아닌 모든 실수
- 부동소수점
  - 컴퓨터가 실수를 표현하는 방법으로, 2진수로 숫자를 표현
  - floating point rounding error(부동소수점과 실수 비교 상황) 주의
- 실수 값을 비교하는 방법
  - 매우 작은 수보다 작은지 확인
  - `math`모듈의 `isclose(a,b)` 를 통해 True, False 확인



#### complex

- 실수부, 허수부로 이루어져 있음
- 허수부는 `j`로 표현

```python
x = 3 + 4j
print(x.real)
print(x.imag)
```

```
3.0
4.0
```



#### Boolean

- `True` , `False` 값을 가진 타입
- 비교, 논리 연산
- False로 반환되는 경우
  - 0, 0.0, (), [], {}, '', None



#### String

- 모든 문자는 str 타입
- 작은 따옴표`'` 또는 큰 따옴표`"` 활용하여 표기
  - 하나의 문장 부호를 활용하여 유지하는 것이 좋음

- 특정 문자, 조작 등을 위해 escape sequence`\` 활용
  - `\n` 줄바꿈, `\t` 탭, `\0` Null, `\\`\, `\'` 작은 따옴표, `\"` 큰 따옴표



#### 📌String Interpolation

- 변수의 값을 문자열의 자리 표시자로 대체하는 방법

  - %-formatting

  ```python
  name = 'Jay'
  print('Hello %s' % name)
  ```

  - str.format()

  ```python
  name = 'Jay'
  print('Hello {}'.format(name))
  ```

  - f-strings (python 3.6+)

  ```python
  name = 'Jay'
  print(f'Hello {name})
  ```



### 📌Type Casting

- 데이터 타입 변환

- 암시적 타입 변환(Implicit)

  - 파이썬 내부적으로 타입 변환

  ```python
  3 + 5.0
  ```

  ```
  8.0
  ```

- 명시적 타입 변환(Explicit)

  - 사용자가 특정 함수 활용해 의도적으로 타입 변환
  - 형식에 맞는 str, float ➡ int
  - 형식에 맞는 str, int ➡ float
  - int, float, list, tuple, dict ➡ str

