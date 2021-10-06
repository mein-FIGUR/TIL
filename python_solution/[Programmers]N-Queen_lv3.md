<https://programmers.co.kr/learn/courses/30/lessons/12952>

<br>

### 📌풀이

----

#### 내가 쓴 풀이(성공)

- 백트래킹 활용
- 방문여부 판단을 `visited`리스트를 만들어 활용
  - 해당 백트래킹을 마친 이후, 변경해준 `visited`를 다시 초기화

```python
def solution(n):
    visited = [-1]*n # 백트래킹을 위한 방문 여부 리스트
    
    def backtracking(r, n):
        res = 0
        if r == n: # 끝까지 탐색한 경우
            return 1
        
        for i in range(n):
            if visited[i] == -1:
                flag = 1
                for j in range(r):
                    now = visited.index(j) # j행의 몇 열인가?
                    if abs(j-r) == abs(now-i): # 대각선으로 만나는지 판단
                        flag = 0
                        break
                
                if flag: # 만나지 않는 경우
                    visited[i] = r # 방문
                    res += backtracking(r+1, n)
                    visited[i] = -1 # 초기화
        
        return res
    
    answer = backtracking(0, n)
    
    return answer
```

<br><br>

### 📌후기

---

백트래킹과 아직 친하지 않지만, 조금 더 친해지기 위해 노력해야겠다! 하는 방식이 조금 더 손에 익어야 할 것 같다..!

