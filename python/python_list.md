# List

- Mutable
- Ordered
- Iterable





### List Method

- `.append(x)` 리스트 끝에 값 추가

```python
l = ['a', 'b', 'c', 'd']
l.append('e')
print(l) #['a', 'b', 'c', 'd', 'e']
```

- `.extend(iterable)` 리스트에 `iterable`항목 추가
  - `['apple']`과 `'apple'`을 extend하는 경우가 다름

```python
l = ['a', 'b', 'c', 'd']
l.extend('egg')
print(l) #['a', 'b', 'c', 'd', 'e', 'g', 'g']
```

- `.insert(idx, x)` 정해진 위치`idx`에 `x` 추가

```python
l = ['a', 'b', 'c', 'd']
l.insert(3,'e')
print(l) #['a', 'b', 'c', 'e', 'd']
```

- `.remove(x)` 리스트에서 값이 `x`인 첫 번째 항목 삭제

```python
l = ['a', 'b', 'c', 'd', 'c']
l.remove('c')
print(l) #['a', 'b', 'd', 'c']
```

- `.pop(i)` 정해진 위치 `i`에 있는 값 삭제 후 리턴
  - `i`가 지정되지 않으면 마지막 항목 삭제 후 리턴

```python
l = ['a', 'b', 'c', 'd', 'c']
l.pop()
print(l) #['a', 'b', 'c', 'd']

l = ['a', 'b', 'c', 'd', 'c']
l.pop(1)
print(l) #['a', 'c', 'd', 'c']
```

- `.clear()` 모든 항목 삭제

```python
l = ['a', 'b', 'c', 'd', 'c']
l.clear()
print(l) #[]
```

- `.index(x)` `x`값을 가진 첫 번째 인덱스 값 반환
  - 없는 경우 ValueError

```python
l = ['a', 'b', 'c', 'd', 'c']
l.index('c') #2
```

- `.count(x)` 원하는 값의 개수를 반환
  - 없는 경우 0

```python
l = ['a', 'b', 'c', 'd', 'c']
l.count('c') #2
```

- `.sort()` 원본 리스트 정렬, None 반환

```python
l = ['a', 'b', 'c', 'd', 'c']
l.sort()
print(l) #['a', 'b', 'c', 'c', 'd']
```

- `.reverse()` 순서를 반대로 뒤집음(정렬하는 것이 아님)

```python
l = ['a', 'b', 'c', 'd', 'c']
l.reverse()
print(l) #['c', 'd', 'c', 'b', 'a']
```













