<https://programmers.co.kr/learn/courses/30/lessons/42627>



### 📌풀이

----

#### 내가 쓴 풀이(성공)

- 문제의 주제처럼, `Heap`을 활용하여 문제 해결
- input data인 `jobs`의 데이터들이 정렬되어 있지 않으므로, 요청 시간을 기준으로 내림차순 정렬
  - 요청 시간이 빠른 순서대로 `jobs`에서 빼기 위함
- 초기화한 힙 `ans`
  - 힙의 우선순위는 작업 소요시간을 기준으로 해야 함
  - `jobs`의 데이터는 `[요청 시간, 소요 시간]` 이므로, 배열을 뒤집어 힙에 `push`
- `ans`에 데이터가 없을 때까지 `while`문 진행
  - `heappop`을 통해 힙 안의 소요 시간이 가장 짧은 데이터를 뽑음
  - 시간 `time`을 작업이 완료된 시간으로 변경
  - 결과값에 `현재 시간 - 요청 시간`을 추가
  - 현재 시간 `time`보다 먼저 요청된 작업이 있는 경우, 힙에 해당 데이터 추가
- 남은 작업이 있지만 힙이 비어 있는 경우(작업이 없는 시간 존재하는 경우)
  - 가장 마지막 `jobs`의 데이터를 꺼내 힙에 추가
  - 현재 시간을 방금 추가한 작업의 요청시간으로 변경

```python
import heapq

def solution(jobs):
    answer = 0
    jobs.sort(key=lambda x: x[0], reverse=True) # 요청 시간 기준 역순 정렬
    n = len(jobs)
    ans = [] # 힙 초기화
    # 작업 소요시간 우선순위를 기준으로 함
    heapq.heappush(ans, jobs.pop()[::-1])
    time = ans[0][1] # 첫 작업 시작시간
    while ans: # 힙에 데이터가 없을 때까지 진행
        now = heapq.heappop(ans)
        time += now[0]
        answer += time-now[1] # 현재시간 - 요청시간
        
        # 현재 시간보다 먼저 요청된 작업 추가
        while jobs and jobs[-1][0] <= time : 
            heapq.heappush(ans, jobs.pop()[::-1])
        
        # 힙은 비어있지만 남은 작업이 있는 경우
        if not ans and jobs:
            heapq.heappush(ans, jobs.pop()[::-1])
            time = ans[0][1] # 현재 시간을 요청 시간으로 변경
        
    return answer//n # 평균 반환
```





### 📌후기

---

heap의 구조, `heapq`의 활용법을 공부하고 풀어본 문제였다! 힙을 활용하여 문제를 푸는 방법을 배울 수 있어서 좋은 문제라고 생각한다. 우선순위를 고려해야 하는 문제라면 앞으로 `heapq`를 잘 활용해야 겠다!