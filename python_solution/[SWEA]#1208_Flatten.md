### πνμ΄

----

#### λ΄κ° μ΄ νμ΄(μ±κ³΅)

```python
for tc in range(1, 11):
    dump_try = int(input())
    boxes = list(map(int, input().split()))
    
    while dump_try > 0 :
        dump_try -= 1
        boxes[boxes.index(max(boxes))] -= 1
        boxes[boxes.index(min(boxes))] += 1
        
    print(f'#{tc} {max(boxes)-min(boxes)}')
```





### πνκΈ°

------

κ°λ‘κΈΈμ΄κ° μ νμ΄ μμ΄μ μκ° μ΄κ³Ό μ΄μκ° μμ΄ ν΄κ²°λ  μ μμλ€!