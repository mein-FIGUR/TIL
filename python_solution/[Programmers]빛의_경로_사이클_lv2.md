<https://programmers.co.kr/learn/courses/30/lessons/86052>

<br>

<br>

### πνμ΄

----

#### λ΄κ° μ΄ νμ΄(μ±κ³΅)

- κ° λ°©ν₯ μ΄λ λ°©λ²μ μ μ₯ν λ¦¬μ€νΈ `d`
- κ²©μμ κ°μ΄ `R`, `L`μΈ κ²½μ°, κ²½λ‘μ λ³κ²½ λ°©λ²μ΄ μ ν λμλλ¦¬ `left`, `right`
  - ex) `right`μμ  keyμΈ 0μ d[0]μ λ§νκ³ , d[0] λ°©ν₯μ `right`μ λ§λλ©΄ valueμΈ 3, μ¦ d[3] λ°©ν₯μΌλ‘ λ°λμ μλ―Έ
- κ° κ²©μμμ λͺ¨λ  λ°©ν₯ νμμ νμλμ§ νλ¨νκΈ° μν λ¦¬μ€νΈ `case`
  - λͺ¨λ  κ°μ 1λ‘ μ΄κΈ°ν
- κ° κ²©μμμ λͺ¨λ  λ°©ν₯μ νμ(Brute Force)
  - ν΄λΉ `case`κ°μ΄ 0μΈ κ²½μ°, μ΄λ―Έ νμν κ²½λ‘μ΄λ―λ‘ `continue`
  - νμνμ§ μμ κ²½μ°, κΈΈμ΄ νλ¨μ μν΄ λ³μ `cnt`λ₯Ό 0μΌλ‘ μ€μ 
  - κ²½λ‘λ₯Ό κ³μ μ΄λνλ©°, μ²μ μμΉλ‘ λμμ¬ λ κΉμ§ `while`λ¬Έ μ§ν
  - μμΉλ₯Ό κ³μ λ°κΎΈκΈ° μν λ³μ `tx`, `ty`, `ti`
    - `ti`λ λ°©ν₯μ λ§ν¨
  - `tx`, `ty`, `ti`κ° κ²©μλ₯Ό λ§λλ©° λ€μ κ²½λ‘μ λ°©ν₯μ λ€μ `tx`, `ty`, `ti`μ μ μ₯

```python
def solution(grid):
    # μ΄λ λ°©ν₯μ© λ¦¬μ€νΈ d
    d = [[-1, 0], [1, 0], [0, 1], [0, -1]]
    # κ²©μμ κ°μ λ°λ₯Έ λ°©ν₯ μ΄λ λ°©λ²
    right = {0: 3, 1: 2, 2: 0, 3: 1}
    left = {0: 2, 1:3, 2: 1, 3: 0}
    
    answer = []
    w, h = len(grid[0]), len(grid)
    # κ° κ²©μμμμ λͺ¨λ  λ°©ν₯μ μ΄λνμλμ§ νλ¨νλ λ¦¬μ€νΈ case
    cases = [[[1]*4 for _ in range(w)] for _ in range(h)]
    for y in range(h):
        for x in range(w):
            for i in range(4):
                # μ΄λ―Έ μ΄λν μ  μλ λ°©ν₯μ νλ¨ X
                if not cases[y][x][i]:
                    continue
                cnt = 0 # κΈΈμ΄ νλ¨μ μν λ³μ
                ty, tx, ti = y, x, i # μμΉ ty, tx, λ°©ν₯ ti
                while True:
                    cases[ty][tx][ti] -= 1
                    cnt += 1
                    now = grid[ty][tx]
                    # νμ¬ κ²©μμ κ°μ νμΈνμ¬ λ°©ν₯ κ²°μ 
                    if now == 'L':
                        ti = left[ti]
                    elif now == 'R' :
                        ti = right[ti]
                    tx, ty = (tx+d[ti][1])%w, (ty+d[ti][0])%h
                    # μ²μ μΆλ°μ μ λμ°©νλ©΄ μλ£
                    if tx == x and ty == y and ti == i:
                        break
                answer.append(cnt)

    # κ°μ μ λ ¬ ν λ¦¬ν΄
    answer.sort()
    return answer
```

<br><br>

### πνκΈ°

---

λ¬Έμ λ₯Ό μ²μ ν΄κ²°ν  λΉμ, μ ν΄κ²°μ΄ λμ§ μμ μλΉν κ³ λ―Όνλ λ¬Έμ μλ€! κ²°κ³Όμ μΌλ‘λ λ¬Έμ λ₯Ό μ λλ‘ μ½μ§ μμμ μ²μμ νλν ν΄κ²°νμ§ λͺ»νμλ€.... λ¬Έμ λ₯Ό λλ°λ‘ λ΄μΌ νλ€λ κ²μ λ€μ ν λ² νμ€ν κΉ¨λ¬μ λ¬Έμ μλ€!

μμ  νμμ ν΅ν΄ ν΄κ²°νμλλ°, λΉμ λ¬Έμ λ₯Ό ν λ 1λ±λΆμ΄ μμ²­ λΉ λ₯΄κ² ν΄κ²°νλλ°,,,, λ°©λ²μ΄ λ¬΄μμΈμ§ μκ³  μΆλ€!