### 📌풀이

----

#### 내가 쓴 풀이(성공)

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





### 📌후기

------

가로길이가 제한이 있어서 시간 초과 이슈가 없이 해결될 수 있었다!