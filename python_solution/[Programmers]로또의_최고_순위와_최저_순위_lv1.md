<https://programmers.co.kr/learn/courses/30/lessons/77484>

<br>

### ๐ํ์ด

----

#### ๋ด๊ฐ ์ด ํ์ด(์ฑ๊ณต)

- ๊ณตํต์ผ๋ก ๊ฐ์ง๊ณ  ์๋ ์ซ์, 0์ ๊ฐ์๋ฅผ ํตํด ๋ฑ์๋ฅผ ํ๋จ ๊ฐ๋ฅ

- `same` : set์ ํ์ฉํ์ฌ ๊ณตํต์ ์ผ๋ก ๊ฐ๊ณ  ์๋ ์ซ์์ ๊ฐ์๋ฅผ ํ์ธ
- `offset`: `lottos`์์ 0์ ๊ฐฏ์ ํ์ธ
- `minimum`: ์ผ์นํ๋ ์ซ์๊ฐ 2 ๋ฏธ๋ง์ธ ๊ฒฝ์ฐ 6๋ฑ, ์ด์ธ์ ๊ฒฝ์ฐ๋ 7-`same`
- `maximum`: `offset`์ด 6์ธ ๊ฒฝ์ฐ ๋ฌด์กฐ๊ฑด 1๋ฑ, ๊ทธ ์ธ์ ๊ฒฝ์ฐ๋ `minimum`-`offset`

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



### ๐ํ๊ธฐ

-----

๋ ๋ฒจ1 ๋ฌธ์ , ๋ฌด๋ํ๊ฒ ํด๊ฒฐํ๋ค!