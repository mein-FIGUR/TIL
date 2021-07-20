# Asterisk`*`

- Asterisk `*`의 사용방법은 여러 종류가 있다.

  - 곱셉, 거듭제곱

  ```python
  a = 2 * 5
  b = 2 ** 5
  ```

  - 리스트 확장

  ```python
  c = [1] * 5
  # [1, 1, 1, 1, 1]
  ```

  - 가변인자
  - unpacking



### 가변 인자

- 길이가 변할 수 있는 argument를 말함
- `*args` , `**kwargs` 와 같은 형태를 자주 볼 수 있음 
  - 가변인자를 사용하겠다는 뜻
- `*` : positional arguments, 값이 없는 경우 error 발생
  - tuple 또는 list 로 저장됨
- `**`: keyword arguments, 값이 없는 경우 default값 사용
  - dict에 저장됨

```python
def function_args(*args):
    print(args)
    
function_args('a','b')
#('a', 'b')
    
def function_kwargs(**kwargs):
    print(kwargs)

function_kwargs(a = 1, b = 2)
#{'a':1, 'b':2}

```





### Unpacking

- list, tuple을 돌면서 값을 출력하는 경우

```python
numbers = [1, 2, 3, 4, 5, 6]
*a, = numbers
print(*a)

*a, b = numbers
print(*a, '///', b)

a, *b, c = numbers
print(a, '/', *b, '/', c)

a, b, *lista, c = numbers
print(a, '/', b, '/', *lista, '/', c)
```

```
1 2 3 4 5 6
1 2 3 4 5 /// 6
1 / 2 3 4 5 / 6
1 / 2 / 3 4 5 / 6
```

