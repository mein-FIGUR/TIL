https://programmers.co.kr/learn/courses/30/lessons/77485





### πνμ΄

----

#### λ΄κ° μ΄ νμ΄(μ±κ³΅)

- κ°μ νμΈνκΈ° μν΄, `box` νλ ¬ κ΅¬ν
- λ¬Έμ μμ μ£Όμ΄μ§ μ‘°κ±΄μ²λΌ κ°μ νμ μν€κ³ , κ°μ₯ μμ κ° `answer`μ μΆκ°

```python
def solution(rows, columns, queries):
    answer = []
    box =[] # νλ ¬ κ° μ€μ 
    for i in range(rows) :
        box.append([])
        for j in range(columns) :
            box[i].append((i)*columns+j+1)
            
    for y1, x1, y2, x2 in queries:
		# x, y : νμ¬ μΈλ±μ€ μμΉ
        # tmpμ κ°μ μ μ₯νλ©° μμΉλ₯Ό λ³κ²½
        # λ³κ²½νλ κ³Όμ μμ λ μμ κ°μ΄ λμ€λ©΄ numμ λ³κ²½
        x, y = x1-1, y1-1
        num = tmp = box[y][x]
        for _ in range(x2-x1):
            nx = x+1
            box[y][nx], tmp = tmp, box[y][nx]
            x = nx
            num = min(num, tmp)
        for _ in range(y2-y1):
            ny = y+1
            box[ny][x], tmp = tmp, box[ny][x]
            y = ny
            num = min(num, tmp)
        for _ in range(x2-x1):
            nx = x-1
            box[y][nx], tmp = tmp, box[y][nx]
            x = nx
            num = min(num, tmp)
        for _ in range(y2-y1):
            ny = y-1
            box[ny][x], tmp = tmp, box[ny][x]
            y = ny
            num = min(num, tmp)
        answer.append(num)    # num μΆκ°
        
    return answer
```







### πνκΈ°

---

μ½λκ° λλ¬΄ ν¬λ°ν κ² κ°λ€....