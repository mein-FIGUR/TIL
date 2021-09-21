<https://programmers.co.kr/learn/courses/30/lessons/86052>

<br>

<br>

### 📌풀이

----

#### 내가 쓴 풀이(성공)

- 각 방향 이동 방법을 저장한 리스트 `d`
- 격자의 값이 `R`, `L`인 경우, 경로의 변경 방법이 적힌 딕셔너리 `left`, `right`
  - ex) `right`에서  key인 0은 d[0]을 말하고, d[0] 방향은 `right`을 만나면 value인 3, 즉 d[3] 방향으로 바뀜을 의미
- 각 격자에서 모든 방향 탐색을 하였는지 판단하기 위한 리스트 `case`
  - 모든 값을 1로 초기화
- 각 격자에서 모든 방향을 탐색(Brute Force)
  - 해당 `case`값이 0인 경우, 이미 탐색한 경로이므로 `continue`
  - 탐색하지 않은 경우, 길이 판단을 위해 변수 `cnt`를 0으로 설정
  - 경로를 계속 이동하며, 처음 위치로 돌아올 때 까지 `while`문 진행
  - 위치를 계속 바꾸기 위한 변수 `tx`, `ty`, `ti`
    - `ti`는 방향을 말함
  - `tx`, `ty`, `ti`가 격자를 만나며 다음 경로와 방향을 다시 `tx`, `ty`, `ti`에 저장

```python
def solution(grid):
    # 이동 방향용 리스트 d
    d = [[-1, 0], [1, 0], [0, 1], [0, -1]]
    # 격자의 값에 따른 방향 이동 방법
    right = {0: 3, 1: 2, 2: 0, 3: 1}
    left = {0: 2, 1:3, 2: 1, 3: 0}
    
    answer = []
    w, h = len(grid[0]), len(grid)
    # 각 격자에서의 모든 방향을 이동하였는지 판단하는 리스트 case
    cases = [[[1]*4 for _ in range(w)] for _ in range(h)]
    for y in range(h):
        for x in range(w):
            for i in range(4):
                # 이미 이동한 적 있는 방향은 판단 X
                if not cases[y][x][i]:
                    continue
                cnt = 0 # 길이 판단을 위한 변수
                ty, tx, ti = y, x, i # 위치 ty, tx, 방향 ti
                while True:
                    cases[ty][tx][ti] -= 1
                    cnt += 1
                    now = grid[ty][tx]
                    # 현재 격자의 값을 확인하여 방향 결정
                    if now == 'L':
                        ti = left[ti]
                    elif now == 'R' :
                        ti = right[ti]
                    tx, ty = (tx+d[ti][1])%w, (ty+d[ti][0])%h
                    # 처음 출발점에 도착하면 완료
                    if tx == x and ty == y and ti == i:
                        break
                answer.append(cnt)

    # 값을 정렬 후 리턴
    answer.sort()
    return answer
```

<br><br>

### 📌후기

---

문제를 처음 해결할 당시, 잘 해결이 되지 않아 상당히 고민했던 문제였다! 결과적으로는 문제를 제대로 읽지 않아서 처음에 한동한 해결하지 못했었다.... 문제를 똑바로 봐야 한다는 것을 다시 한 번 확실히 깨달은 문제였다!

완전 탐색을 통해 해결하였는데, 당시 문제를 풀 때 1등분이 엄청 빠르게 해결하던데,,,, 방법이 무엇인지 알고 싶다!