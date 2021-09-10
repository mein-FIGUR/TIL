<https://www.acmicpc.net/problem/1260>



### 📌풀이

----

#### 내가 쓴 풀이(성공)

- 각 정점에 연결된 정점들의 리스트를 딕셔너리로 구현
- 정점의 번호가 작은 것부터 탐색한다고 하였으므로, 각 리스트들을 정렬
- dfs, bfs 진행

```python
from collections import deque

n, m, v = map(int, input().split())
connected = {i: [] for i in range(1, n + 1)}
for _ in range(m):
    n1, n2 = map(int, input().split())
    connected[n1].append(n2)
    connected[n2].append(n1)

for n in range(1, n+1):
    connected[n].sort()


def bfs(v):
    res = []
    visited = [0] * n
    dq = deque()
    dq.append(v)
    while dq:
        now = dq.popleft()
        res.append(now)
        visited[now - 1] = 1
        for node in connected[now]:
            if not visited[node - 1] and node not in dq:
                dq.append(node)
    return res


def dfs(v, visited=[]):
    visited.append(v)
    for node in connected[v]:
        if node not in visited:
            dfs(node, visited)
    return visited


print(*dfs(v))
print(*bfs(v))
```





### 📌후기

---

Django 공부하느라 알고리즘 감이 다 죽었다.... 문제를 더 많이 풀어야 겠다ㅠㅠㅠㅠ