<https://programmers.co.kr/learn/courses/30/lessons/76502>



### 📌풀이

----

#### 내가 쓴 풀이(성공)

- `deque`를 이용해 문자열의 맨 앞의 값을 맨 뒤로 넣어주고, `join` 활용
- 문자열이 올바른 괄호 문자열인지 판단하는 함수 `check`
  - 각 괄호의 일치 여부를 통해 참 , 거짓 여부 판단
  - 열린 괄호는 `stack`안에, 닫힌 괄호가 나오면 가장 마지막 괄호를 빼서 올바른지 판단
  - 모든 과정을 거친 후, `stack`에 괄호가 남아있다면 거짓
  - 닫힌 괄호가 나왔는데 `stack`에 아무것도 없다면 거짓

```python
from collections import deque

def check(string): # 올바른 괄호 문자열인지 판단하는 함수
    stack = []
    for s in string:
        if s in "({[":
            stack.append(s)
        elif not stack:
            return 0
        elif s == ')':
            if stack[-1] == '(':
                stack.pop()
            else :
                return 0
        elif s == '}':
            if stack[-1] == '{':
                stack.pop()
            else :
                return 0
        else :
            if stack[-1] == '[':
                stack.pop()
            else :
                return 0
    if stack:
        return 0
    return 1

def solution(s):
    answer = 0
    dq_s = deque(s)
    for _ in range(len(s)):
        if check(''.join(dq_s)): # 각 문자열 괄호 판단
            answer += 1 # 사실이면 정답에 1 추가
        dq_s.append(dq_s.popleft()) # 맨 앞의 괄호를 맨 뒤로 이동
    return answer
```





### 📌후기

---

`deque`를 활용해 무난히 해결할 수 있었지만, 뭔가 아쉬운 코드였다...! 고칠 점이 있나 봐야겠다!