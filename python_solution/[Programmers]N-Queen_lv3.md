<https://programmers.co.kr/learn/courses/30/lessons/12952>

<br>

### ๐ํ์ด

----

#### ๋ด๊ฐ ์ด ํ์ด(์ฑ๊ณต)

- ๋ฐฑํธ๋ํน ํ์ฉ
- ๋ฐฉ๋ฌธ์ฌ๋ถ ํ๋จ์ `visited`๋ฆฌ์คํธ๋ฅผ ๋ง๋ค์ด ํ์ฉ
  - ํด๋น ๋ฐฑํธ๋ํน์ ๋ง์น ์ดํ, ๋ณ๊ฒฝํด์ค `visited`๋ฅผ ๋ค์ ์ด๊ธฐํ

```python
def solution(n):
    visited = [-1]*n # ๋ฐฑํธ๋ํน์ ์ํ ๋ฐฉ๋ฌธ ์ฌ๋ถ ๋ฆฌ์คํธ
    
    def backtracking(r, n):
        res = 0
        if r == n: # ๋๊น์ง ํ์ํ ๊ฒฝ์ฐ
            return 1
        
        for i in range(n):
            if visited[i] == -1:
                flag = 1
                for j in range(r):
                    now = visited.index(j) # jํ์ ๋ช ์ด์ธ๊ฐ?
                    if abs(j-r) == abs(now-i): # ๋๊ฐ์ ์ผ๋ก ๋ง๋๋์ง ํ๋จ
                        flag = 0
                        break
                
                if flag: # ๋ง๋์ง ์๋ ๊ฒฝ์ฐ
                    visited[i] = r # ๋ฐฉ๋ฌธ
                    res += backtracking(r+1, n)
                    visited[i] = -1 # ์ด๊ธฐํ
        
        return res
    
    answer = backtracking(0, n)
    
    return answer
```

<br><br>

### ๐ํ๊ธฐ

---

๋ฐฑํธ๋ํน๊ณผ ์์ง ์นํ์ง ์์ง๋ง, ์กฐ๊ธ ๋ ์นํด์ง๊ธฐ ์ํด ๋ธ๋ ฅํด์ผ๊ฒ ๋ค! ํ๋ ๋ฐฉ์์ด ์กฐ๊ธ ๋ ์์ ์ต์ด์ผ ํ  ๊ฒ ๊ฐ๋ค..!

