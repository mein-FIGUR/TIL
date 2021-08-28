<https://programmers.co.kr/learn/courses/30/lessons/42628>



### 📌풀이

----

#### 내가 쓴 풀이(성공)

- 최소 힙 `hq_min`, 최대 힙 `hq_max`을 각각 만들어 판단
- 원소의 개수는 `cnt`라는 변수를 따로 만들어 판단
  - `cnt`가 0인 경우, 힙을 초기화
- `operations`의 명령어에 따라, push와 pop 진행
  - `cnt`가 0인데 pop 명령어가 들어온 경우, 무시

```python
import heapq

def solution(operations):
    answer = [0, 0] 
    cnt = 0 # 현재 힙 안의 원소 개수 판단을 위한 변수
    for op in operations:
        if cnt == 0 : # 힙이 비어있는 경우, 최대 힙, 최소 힙 초기화
            hq_max, hq_min = [], []
        
        if op[0] == 'I': # push
            cnt += 1 
            heapq.heappush(hq_min, int(op[2:]))
            heapq.heappush(hq_max, -int(op[2:]))
        elif cnt == 0 : # 힙이 비어있는데 pop을 하는 경우, 무시
            continue
        elif op[2] == '-': # 최소값 pop
            heapq.heappop(hq_min)
            cnt -= 1
        else : # 최대값 pop
            heapq.heappop(hq_max)
            cnt -= 1

    
    if cnt == 1: # 원소가 하나 남은 경우, 최대값, 최소값 동일
        answer[0] = answer[1] = heapq.heappop(hq_min)
    elif cnt >= 2: # 원소가 2개 이상 남은 경우 [최대값, 최소값]
        answer[0] = -heapq.heappop(hq_max)
        answer[1] = heapq.heappop(hq_min)
    
    return answer
```







### 📌후기

---

무난하게 해결할 수 있을 줄 알았으나, 값이 들어왔다가 모두 다 pop이 되어 다시 빈 상태가 되고, 이후 다시 값이 들어오는 구조의 경우를 잡지 못했었다. 이러한 부분을 처리하기 위해, for문의 초반부에 `cnt`가 0인 경우 초기화를 하는 부분을 두어 예외를 처리할 수 있었다!

질문하기 탭의 케이스를 적용하여 겨우 해결할 수 있었는데, 도움을 받는 일을 줄여야 겠다!