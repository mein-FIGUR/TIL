<https://programmers.co.kr/learn/courses/30/lessons/76502>



### ๐ํ์ด

----

#### ๋ด๊ฐ ์ด ํ์ด(์ฑ๊ณต)

- `deque`๋ฅผ ์ด์ฉํด ๋ฌธ์์ด์ ๋งจ ์์ ๊ฐ์ ๋งจ ๋ค๋ก ๋ฃ์ด์ฃผ๊ณ , `join` ํ์ฉ
- ๋ฌธ์์ด์ด ์ฌ๋ฐ๋ฅธ ๊ดํธ ๋ฌธ์์ด์ธ์ง ํ๋จํ๋ ํจ์ `check`
  - ๊ฐ ๊ดํธ์ ์ผ์น ์ฌ๋ถ๋ฅผ ํตํด ์ฐธ , ๊ฑฐ์ง ์ฌ๋ถ ํ๋จ
  - ์ด๋ฆฐ ๊ดํธ๋ `stack`์์, ๋ซํ ๊ดํธ๊ฐ ๋์ค๋ฉด ๊ฐ์ฅ ๋ง์ง๋ง ๊ดํธ๋ฅผ ๋นผ์ ์ฌ๋ฐ๋ฅธ์ง ํ๋จ
  - ๋ชจ๋  ๊ณผ์ ์ ๊ฑฐ์น ํ, `stack`์ ๊ดํธ๊ฐ ๋จ์์๋ค๋ฉด ๊ฑฐ์ง
  - ๋ซํ ๊ดํธ๊ฐ ๋์๋๋ฐ `stack`์ ์๋ฌด๊ฒ๋ ์๋ค๋ฉด ๊ฑฐ์ง

```python
from collections import deque

def check(string): # ์ฌ๋ฐ๋ฅธ ๊ดํธ ๋ฌธ์์ด์ธ์ง ํ๋จํ๋ ํจ์
    stack = []
    for s in string:
        if s in "({[":
            stack.append(s)
        elif not stack:
            return 0
        elif s == ')':
            if stack[-1] == '(':
                stack.pop()
            else :
                return 0
        elif s == '}':
            if stack[-1] == '{':
                stack.pop()
            else :
                return 0
        else :
            if stack[-1] == '[':
                stack.pop()
            else :
                return 0
    if stack:
        return 0
    return 1

def solution(s):
    answer = 0
    dq_s = deque(s)
    for _ in range(len(s)):
        if check(''.join(dq_s)): # ๊ฐ ๋ฌธ์์ด ๊ดํธ ํ๋จ
            answer += 1 # ์ฌ์ค์ด๋ฉด ์ ๋ต์ 1 ์ถ๊ฐ
        dq_s.append(dq_s.popleft()) # ๋งจ ์์ ๊ดํธ๋ฅผ ๋งจ ๋ค๋ก ์ด๋
    return answer
```





### ๐ํ๊ธฐ

---

`deque`๋ฅผ ํ์ฉํด ๋ฌด๋ํ ํด๊ฒฐํ  ์ ์์์ง๋ง, ๋ญ๊ฐ ์์ฌ์ด ์ฝ๋์๋ค...! ๊ณ ์น  ์ ์ด ์๋ ๋ด์ผ๊ฒ ๋ค!