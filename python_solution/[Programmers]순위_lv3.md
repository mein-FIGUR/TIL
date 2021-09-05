https://programmers.co.kr/learn/courses/30/lessons/49191



### 📌풀이

----

#### 내가 쓴 풀이(성공)

- 한 선수가 이긴 선수들, 진 선수들 목록을 생성(`set`활용)
- `i`번 선수가 이긴 선수들은, `i`번 선수가 진 선수들한테도 짐
- `i`번 선수가 진 선수들은, `i`번 선수가 이긴 선수들한테도 이김

- 위의 두 내용을 업데이트하고, 이긴 선수 + 진 선수의 수가 `n-1`이면 순위를 알 수 있다.

```python
def solution(n, results):
    win_dic = {i:set() for i in range(1, n+1)} # key가 이긴 선수들 목록
    lose_dic = {i:set() for i in range(1, n+1)} # key가 진 선수들 목록
    for start, end in results: # 경우의 수 추가
        win_dic[start].add(end)
        lose_dic[end].add(start)

    for i in range(1, n+1):
        # i가 이긴 선수들의 진 목록에는 i가 진 선수들도 추가
        for loser in win_dic[i]: 
            lose_dic[loser].update(lose_dic[i])
        # i가 진 선수들의 이긴 목록에는 i가 이긴 선수들도 추가
        for winner in lose_dic[i]:
            win_dic[winner].update(win_dic[i])
            
    answer = 0
    # 이긴 선수 + 진 선수의 합이 n-1이면, 순위를 알 수 있음
    for i in range(1, n+1):
        if len(win_dic[i]) + len(lose_dic[i]) == n-1:
            answer += 1
    
    return answer
```





### 📌후기

----

스스로 해결하는 능력도 더 키워야 겠다... 시간이 촉박하다고 너무 풀이에 의존하지 말자!