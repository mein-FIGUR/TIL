### πνμ΄

----

#### λ΄κ° μ΄ νμ΄(μ±κ³΅, λ³΅μ‘)

- μμλ€μ μνλ₯Ό λ³κ²½νλ©° μ§ννλ λ°©μ
- μμμ λ°°μ΄μ λ°κΎΈκ³ (μν --> μ’μ°), μΈλ±μ€μ μμͺ½κ³Ό λ€μͺ½μμ μ κ·Ό
  - μμͺ½ κΈ°μ€ Sκ·Ήμ λ§λλ κ²½μ°, μ κ±°, Nκ·Ήμ λ§λλ κ²½μ° λ©μΆ€
  - λ·μͺ½ κΈ°μ€ Nκ·Ήμ λ§λλ κ²½μ°, μ κ±°, Sκ·Ήμ λ§λλ κ²½μ° λ©μΆ€
- μ¬λΌμ§ μμλ€μ μ κ±°ν ν, λ¨μ μμλ€μ νλλ‘ ν©μΉ ν, κ΅μ°© μνλ₯Ό νμ
  - νμλ κ΅μ°©μνμ μλ₯Ό νμΈ

```python
for tc in range(1, 11):
    n = int(input())
    arr = [list(map(int, input().split())) for _ in range(n)]  # 1: N, 2: S
    mag = list(map(list, zip(*arr)))  # transpose
 
    total_res = 0
    for i in range(n):
        idx = 0 # μμͺ½λΆν° νλ¨
        bidx = n - 1 # λ€μͺ½λΆν° νλ¨
        while idx < n: # Sλ₯Ό λ§λλ©΄ μ κ±°, Nμ λ§λλ©΄ λ©μΆ€
            if mag[i][idx] == 2:
                mag[i][idx] = 0
            elif mag[i][idx] == 1:
                break
            idx += 1
        while bidx >= 0: # Nμ λ§λλ©΄ μ κ±°, Sλ₯Ό λ§λλ©΄ λ©μΆ€
            if mag[i][bidx] == 1:
                mag[i][bidx] = 0
            elif mag[i][bidx] == 2:
                break
            bidx -= 1
 
        res = ''
        for idx in range(n): # λ¨μ μμλ€μ νλμ λ¬Έμμ΄λ‘ ν©μΉ¨
            if mag[i][idx]: 
                res += str(mag[i][idx])
        res = res.replace('12', 'X') # κ΅μ°© μν νμ
        total_res += res.count('X') # κ΅μ°© μν κ°μ μΆκ°
         
    print(f'#{tc} {total_res}')
```

- λ€λ₯Έ μ¬λμ νμ΄λ₯Ό λ³΄κ³ , λΆνμν κ³Όμ μ΄ μλΉν λ§μμ μκ² λμλ€...





#### λ΄κ° μ΄ νμ΄ + λ€λ₯Έ μ¬λμ νμ΄ μ μ©(μ±κ³΅)

- `flag`: κ΅μ°© μν νμΈμ μν λ³μ
- Nκ·Ήμ λ§λλ©΄ `flag`λ₯Ό νμ±ν μν€κ³ , κ·Έ μνμμ Sκ·Ήμ λ§λλ©΄ κ΅μ°©μν
  - μ΄ν `flag`λ₯Ό μ΄κΈ°ν

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





### πνκΈ°

----

λλ¦ κ΄μ°?κ² ν΄κ²°νλ€κ³  μκ°νλλ°, λ€λ₯Έ μ¬λμ νμ΄κ° λ κ΄μ°?μ μ μ νμΈνλ€! λ κ°λ¨ν λ°©λ²μ λλκ³  μμ²­ λμμ ν΄κ²°ν λλ...κ·Έλλ μμ¬μ΄ μ μ νμΈν  μ μμ΄ μ’μ λ¬Έμ μλ€!