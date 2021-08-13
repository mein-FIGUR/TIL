### 📌풀이

----

#### 내가 쓴 풀이(성공)

```python
for tc in range(1, 11):
    n = int(input())
    arr = []
    for _ in range(100):
        arr.append(list(map(int, input().split())))
    
    idx = 99 # idx : 시작하는 y값
    x = arr[idx].index(2) # x : 맨 끝 도착점의 x값
    for idx in range(99, -1, -1):
        left = x-1
        right = x+1 
        # 왼쪽에 값이 존재하는 경우, 왼쪽으로 도착할때까지 이동
        if 0<=left<100 and arr[idx][left]:
            # 올라가는 곳이 있으면 정지
            while not arr[idx-1][left]:
                left -= 1
            x = left
        # 오른쪽에 값이 존재하는 경우, 오른쪽으로 도착할때까지 이동        
        elif 0<=right<100 and arr[idx][right]:
            # 올라가는 곳이 있으면 정지
            while not arr[idx-1][right]:
                right += 1
            x = right

            
    print(f'#{n} {x}')
```

- 도착점부터 값을 읽어감
- 왼쪽이나 오른쪽으로 움직이는 구간이 있는 경우, 위로 올라가는 구간이 나올때까지 이동





### 📌후기

----

은근 스트레스 많이 받았던 문제,,, 코드를 이상하게 짜서 제출조차 되지 않는 상황이 되었었다. 처음에는 테스트케이스가 너무 커서 그런 이유로 발생한 오류인줄 알았지만, 역시 내 문제였던 걸로....그래도 해결해서 다행이다!