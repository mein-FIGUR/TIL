### 📌풀이

----

#### 내가 쓴 풀이(성공, 복잡)

- 자석들의 상태를 변경하며 진행하는 방식
- 자석의 배열을 바꾸고(상하 --> 좌우), 인덱스의 앞쪽과 뒤쪽에서 접근
  - 앞쪽 기준 S극을 만나는 경우, 제거, N극을 만나는 경우 멈춤
  - 뒷쪽 기준 N극을 만나는 경우, 제거, S극을 만나는 경우 멈춤
- 사라진 자석들을 제거한 후, 남은 자석들을 하나로 합친 후, 교착 상태를 표시
  - 표시된 교착상태의 수를 확인

```python
for tc in range(1, 11):
    n = int(input())
    arr = [list(map(int, input().split())) for _ in range(n)]  # 1: N, 2: S
    mag = list(map(list, zip(*arr)))  # transpose
 
    total_res = 0
    for i in range(n):
        idx = 0 # 앞쪽부터 판단
        bidx = n - 1 # 뒤쪽부터 판단
        while idx < n: # S를 만나면 제거, N을 만나면 멈춤
            if mag[i][idx] == 2:
                mag[i][idx] = 0
            elif mag[i][idx] == 1:
                break
            idx += 1
        while bidx >= 0: # N을 만나면 제거, S를 만나면 멈춤
            if mag[i][bidx] == 1:
                mag[i][bidx] = 0
            elif mag[i][bidx] == 2:
                break
            bidx -= 1
 
        res = ''
        for idx in range(n): # 남은 자석들을 하나의 문자열로 합침
            if mag[i][idx]: 
                res += str(mag[i][idx])
        res = res.replace('12', 'X') # 교착 상태 표시
        total_res += res.count('X') # 교착 상태 개수 추가
         
    print(f'#{tc} {total_res}')
```

- 다른 사람의 풀이를 보고, 불필요한 과정이 상당히 많음을 알게 되었다...





#### 내가 쓴 풀이 + 다른 사람의 풀이 적용(성공)

- `flag`: 교착 상태 확인을 위한 변수
- N극을 만나면 `flag`를 활성화 시키고, 그 상태에서 S극을 만나면 교착상태
  - 이후 `flag`를 초기화

```python
for tc in range(1, 11):
    n = int(input())
    mag = [list(map(int, input().split())) for _ in range(n)]  # 1: N, 2: S
 
    total_res = 0
    for i in range(n):
        flag = 0
        for j in range(n):
            if mag[j][i] == 1:
                flag = 1
            elif mag[j][i] == 2:
                if flag :
                    total_res += 1
                    flag = 0
 
    print(f'#{tc} {total_res}')
```





### 📌후기

----

나름 괜찮게 해결했다고 생각했는데, 다른 사람의 풀이가 더 괜찮은 점을 확인했다! 더 간단한 방법을 놔두고 엄청 돌아서 해결한 느낌...그래도 아쉬운 점을 확인할 수 있어 좋은 문제였다!