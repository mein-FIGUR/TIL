### πνμ΄

----

#### λ΄κ° μ΄ νμ΄(μ±κ³΅)

```python
for _ in range(10):
    case_number = int(input())
    array = []
    
    #λ°°μ΄ μμ±
    for _ in range(100):
        l = list(map(int,input().split()))
        array.append(l)
        
    array_max = 0
    
    calc_3, calc_4 = 0, 0
    for idx1 in range(100):
        
        #κ°λ‘ μ΅λκ° νμΈ
        calc_1 = sum(array[idx1])
        if calc_1 > array_max:
            array_max = calc_1
        
        #μΈλ‘ μ΅λκ° νμΈ
        calc_2 = 0
        for idx2 in range(100):
            calc_2 += array[idx2][idx1]
        if calc_2 > array_max:
            array_max = calc_2
        
        #λκ°μ  2κ°
        calc_3 += array[idx1][idx1]
        calc_4 += array[idx1][99-idx1]
        
    if calc_3 > array_max:
        array_max = calc_3
        
    if calc_4 > array_max:
        array_max = calc_4
        
    print(f'#{case_number} {array_max}')
```





### πνκΈ°

------

λ¬΄λλ¬΄λνλ€!
