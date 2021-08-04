### 📌풀이

----

#### 내가 쓴 풀이(성공)

```python
T = int(input())

#정렬을 위한 딕셔너리
num_dict = {"ZRO": 0, "ONE": 1, "TWO": 2, "THR": 3, "FOR": 4, "FIV": 5, "SIX": 6, "SVN": 7, "EGT": 8, "NIN": 9 }

for test_case in range(1, T+1):
    num, N = input().split()
    #문자열을 리스트로 받아옴
    num_list = list(input().split())
    
    #리스트를 딕셔너리의 value를 기준으로 정렬 후 출력
    num_list.sort(key=lambda x : num_dict[x])
    print(num)
    print(' '.join(num_list))
```

- 정렬을 위한 딕셔너리 `num_dict`를 설정
- 인풋으로 받아온 문자열을 리스트로 바꿔 저장 후 정렬
  - 정렬 기준은 `num_dict`의 values



### 📌후기

----

백준 문제 중 [크로아티아 알파벳](https://velog.io/@mein-figur/BOJPython%ED%81%AC%EB%A1%9C%EC%95%84%ED%8B%B0%EC%95%84-%EC%95%8C%ED%8C%8C%EB%B2%B3-2941), 카카오 채용연계형 문제 중 [숫자 문자열과 영단어](https://velog.io/@mein-figur/ProgrammersPython%EC%88%AB%EC%9E%90-%EB%AC%B8%EC%9E%90%EC%97%B4%EA%B3%BC-%EC%98%81%EB%8B%A8%EC%96%B4) 에서 해결한 방식을 적용하였다. 위의 두 문제에서는 딕셔너리를 만들고, replace를 활용하였다면, 여기서는 sort의 기준으로 활용하였다. 풀었던 유형을 떠올리며 해결해서 의미있었던 문제였다!