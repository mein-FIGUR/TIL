### 📌풀이

----

#### 내가 쓴 풀이(성공)

```python
for tc in range(1, 11):
    num = int(input())
    buildings = list(map(int, input().split()))
    
    views = 0
    left, right = 0, 0
    for idx in range(2, num-2):
        # 양쪽 2개의 기둥에서 최대 값 측정
        left = buildings[idx-1] if buildings[idx-1] > buildings[idx-2] else buildings[idx-2]
        right = buildings[idx+1] if buildings[idx+1] > buildings[idx+2] else buildings[idx+2]
        top = left if left > right else right
        
        #양쪽 기둥의 최대값보다 빌딩이 더 높은 경우, view 추가
        if buildings[idx] > top :
            views += buildings[idx] - top
    print(f'#{tc} {views}')
```





### 📌후기

----

min, max를 활용하지 않고 구현을 해보려고 했는데, 그러다보니 코드가 살짝 길어진 감이 있는 것 같다.