https://programmers.co.kr/learn/courses/30/lessons/77485





### 📌풀이

----

#### 내가 쓴 풀이(성공)

- 값을 확인하기 위해, `box` 행렬 구현
- 문제에서 주어진 조건처럼 값을 회전시키고, 가장 작은 값 `answer`에 추가

```python
def solution(rows, columns, queries):
    answer = []
    box =[] # 행렬 값 설정
    for i in range(rows) :
        box.append([])
        for j in range(columns) :
            box[i].append((i)*columns+j+1)
            
    for y1, x1, y2, x2 in queries:
		# x, y : 현재 인덱스 위치
        # tmp에 값을 저장하며 위치를 변경
        # 변경하는 과정에서 더 작은 값이 나오면 num을 변경
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
        answer.append(num)    # num 추가
        
    return answer
```







### 📌후기

---

코드가 너무 투박한 것 같다....