# Set

- Mutable
- Unordered
- Iterable



### Set Method

- `.add(x)` set에 `x` 추가

```python
s = {2, 9, 4}
s.add(3)
print(s) #{9, 2, 3, 4}
```

- `.update(*x)` 여러 값을 추가

```python
s = {2, 9, 3}
s.update('a', 'bd')
print(s) #{2, 3, 9, 'a', 'd', 'b'}
```

- `.remove(x)` set에서 `x`제거, 없으면 KeyError

```python
s = {2, 9, 3}
s.remove(3)
print(s) #{9, 2}
```

- `.discard(x)` set에서 `x`제거, 없어도 에러 X

```python
s = {2, 9, 3}
s.discard(10)
print(s) #{9, 2, 3}
s.discard(2)
print(s) #{9, 3}
```

- `.pop()` 임의의 원소 제거, 비어있는 경우 KeyError

```python
s = {2, 9, 3}
s.pop()
print(s) #{2, 3}, 임의로 하나가 없어짐
```





# Dictionary

- key, value로 구성되어 있음
- Mutable
- Unordered
- Iterable
  - 기본적으로 key를 순회



### Dictionary Method

- `.get(key [, default])` `key`를 통해 `value`를 가져옴
  - `key`가 딕셔너리에 없어도 KeyError 발생 X, `None`반환

```python
dic = {'a': 10, 'b':[1, 2], 'c':{3:'b'}}
dic.get('b') #[1, 2]
```

- `.pop(key [, default])` key가 딕셔너리에 있으면 제거하고 반환
  - 없으면 default 반환, default 없으면 KeyError

```python
dic = {'a': 10, 'b':[1, 2], 'c':{3:'b'}}
dic.pop('b')
print(dic) #{'a': 10, 'c': {3: 'b'}}
```

- `.update(key = 'value')` 값을 제공하는 key, value로 갱신
  - 기존 `key`는 덮어씀


```python
dic = {'a': 10, 'b':[1, 2], 'c':{3:'b'}}
dic.update(b=30)
print(dic) #{'a': 10, 'b': 30, 'c': {3: 'b'}}
```

- `.keys()` `key`로 구성된 결과

```python
dic = {'a': 10, 'b':[1, 2], 'c':{3:'b'}}
dic.keys() #dict_keys(['a', 'b', 'c'])
```

- `.values()` `value`로 구성된 결과

```python
dic = {'a': 10, 'b':[1, 2], 'c':{3:'b'}}
dic.values() #dict_values([10, [1, 2], {3: 'b'}])
```

- `.items()` `(key, value)`로 구성된 결과

```python
dic = {'a': 10, 'b':[1, 2], 'c':{3:'b'}}
dic.items() 
#dict_items([('a', 10), ('b', [1, 2]), ('c', {3: 'b'})])
```















