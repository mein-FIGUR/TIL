### ๐ํ์ด

----

#### ๋ด๊ฐ ์ด ํ์ด(์ฑ๊ณต)

```python
for tc in range(1, 11):
    num = int(input())
    buildings = list(map(int, input().split()))
    
    views = 0
    left, right = 0, 0
    for idx in range(2, num-2):
        # ์์ชฝ 2๊ฐ์ ๊ธฐ๋ฅ์์ ์ต๋ ๊ฐ ์ธก์ 
        left = buildings[idx-1] if buildings[idx-1] > buildings[idx-2] else buildings[idx-2]
        right = buildings[idx+1] if buildings[idx+1] > buildings[idx+2] else buildings[idx+2]
        top = left if left > right else right
        
        #์์ชฝ ๊ธฐ๋ฅ์ ์ต๋๊ฐ๋ณด๋ค ๋น๋ฉ์ด ๋ ๋์ ๊ฒฝ์ฐ, view ์ถ๊ฐ
        if buildings[idx] > top :
            views += buildings[idx] - top
    print(f'#{tc} {views}')
```





### ๐ํ๊ธฐ

----

min, max๋ฅผ ํ์ฉํ์ง ์๊ณ  ๊ตฌํ์ ํด๋ณด๋ ค๊ณ  ํ๋๋ฐ, ๊ทธ๋ฌ๋ค๋ณด๋ ์ฝ๋๊ฐ ์ด์ง ๊ธธ์ด์ง ๊ฐ์ด ์๋ ๊ฒ ๊ฐ๋ค.