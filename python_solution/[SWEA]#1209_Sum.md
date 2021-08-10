### 📌풀이

----

#### 내가 쓴 풀이(성공)

```python
for _ in range(10):
    case_number = int(input())
    array = []
    
    #배열 생성
    for _ in range(100):
        l = list(map(int,input().split()))
        array.append(l)
        
    array_max = 0
    
    calc_3, calc_4 = 0, 0
    for idx1 in range(100):
        
        #가로 최대값 확인
        calc_1 = sum(array[idx1])
        if calc_1 > array_max:
            array_max = calc_1
        
        #세로 최대값 확인
        calc_2 = 0
        for idx2 in range(100):
            calc_2 += array[idx2][idx1]
        if calc_2 > array_max:
            array_max = calc_2
        
        #대각선 2개
        calc_3 += array[idx1][idx1]
        calc_4 += array[idx1][99-idx1]
        
    if calc_3 > array_max:
        array_max = calc_3
        
    if calc_4 > array_max:
        array_max = calc_4
        
    print(f'#{case_number} {array_max}')
```





### 📌후기

------

무난무난했다!
