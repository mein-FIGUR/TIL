<https://www.acmicpc.net/problem/1260>



### πνμ΄

----

#### λ΄κ° μ΄ νμ΄(μ±κ³΅)

- κ° μ μ μ μ°κ²°λ μ μ λ€μ λ¦¬μ€νΈλ₯Ό λμλλ¦¬λ‘ κ΅¬ν
- μ μ μ λ²νΈκ° μμ κ²λΆν° νμνλ€κ³  νμμΌλ―λ‘, κ° λ¦¬μ€νΈλ€μ μ λ ¬
- dfs, bfs μ§ν

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





### πνκΈ°

---

Django κ³΅λΆνλλΌ μκ³ λ¦¬μ¦ κ°μ΄ λ€ μ£½μλ€.... λ¬Έμ λ₯Ό λ λ§μ΄ νμ΄μΌ κ² λ€γ γ γ γ 