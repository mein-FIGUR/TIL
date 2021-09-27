<https://programmers.co.kr/learn/courses/30/lessons/77484>

<br>

### 📌풀이

----

#### 내가 쓴 풀이(성공)

- 공통으로 가지고 있는 숫자, 0의 개수를 통해 등수를 판단 가능

- `same` : set을 활용하여 공통적으로 갖고 있는 숫자의 개수를 확인
- `offset`: `lottos`에서 0의 갯수 확인
- `minimum`: 일치하는 숫자가 2 미만인 경우 6등, 이외의 경우는 7-`same`
- `maximum`: `offset`이 6인 경우 무조건 1등, 그 외의 경우는 `minimum`-`offset`

```python
def solution(lottos, win_nums):
    same = len(set(lottos) & set(win_nums))
    offset = lottos.count(0)
    minimum = 7-same if same > 1 else 6
    maximum = minimum - offset if offset < 6 else 1
    return [maximum, minimum]
```

<br>

<br>



### 📌후기

-----

레벨1 문제, 무난하게 해결했다!