## Binary Search(이진 탐색)

- 자료의 가운데에 있는 항목의 키 값과 비교하여 다음 검색의 위치 결정
  - 범위를 계속 반으로 줄여가면서 탐색
- 자료가 정렬된 상태여야 함



### Algorithm

```python
a = [2, 4, 7, 9, 10, 13]


def binary_search(a, num): # 재귀 쓰지 않은 함수
    # 시작 인덱스, 맨 끝 인덱스
    start, end = 0, len(a)-1

    # 시작 인덱스가 끝 인덱스를 넘지 않는 경우
    while start <= end :
        # 중간 인덱스 확인
        middle = (start + end)//2

        # 값을 찾았다면, True를 리턴
        if a[middle] == num :
            return True
        # 중간값이 찾고자 하는 숫자보다 크다면, 앞부분 확인
        elif a[middle] > num :
            end = middle - 1
        # 중간값이 찾고자 하는 숫자보다 작다면, 뒷부분 확인
        else :
            start = middle + 1

    return False


print(binary_search(a, 11)) # False
print(binary_search(a, 4)) # True


def binary_search_2(a, num, start, end): # 재귀 활용
    # 시작 인덱스가 끝 인덱스보다 크다면, False 리턴
    if start > end :
        return False

    # 중간 인덱스 확인
    middle = (start+end)//2
    # 값을 찾았다면, True를 리턴
    if a[middle] == num :
        return True
    # 중간값이 찾고자 하는 숫자보다 크다면, 앞부분 확인(end값 변경)
    elif a[middle] > num :
        return binary_search_2(a, num, start, middle -1)
    # 중간값이 찾고자 하는 숫자보다 작다면, 뒷부분 확인(start값 변경)
    else :
        return binary_search_2(a, num, middle + 1, end)


print(binary_search_2(a, 11, 0, len(a))) # False
print(binary_search_2(a, 4, 0, len(a))) # True
```



### bisect

- 이진탐색을 위한 모듈

```python
import bisect

a = [2, 4, 4, 7, 10, 13]

# bisect : 인덱스 반환
# 리스트 a에 3을 넣을 위치 인덱스 반환
# 같은 값이 없는 경우
print(bisect.bisect_left(a, 3)) # 1

# 리스트 a에 4를 넣을 위치 인덱스 반환
# 같은 값이 있는 경우, 왼쪽
print(bisect.bisect_left(a, 4)) # 1

# 같은 값이 있는 경우, 오른쪽
print(bisect.bisect_right(a, 4)) # 3

# 같은 값이 있는 경우, 오른쪽 (bisect_right와 동일)
print(bisect.bisect(a, 4)) # 3

# insort
# 리스트에 집어넣는 과정까지 진행
# bisect와 마찬가지로 insort_left, insort_right 존재
bisect.insort(a, 3)
print(a) # [2, 3, 4, 4, 7, 10, 13]

```

