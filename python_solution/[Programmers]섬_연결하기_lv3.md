https://programmers.co.kr/learn/courses/30/lessons/42861



### 📌풀이

----

#### 내가 쓴 풀이(성공)

- kruskal 알고리즘 활용
  - `costs`를 cost가 작은 값 기준으로 정렬
- 부모 노드를 저장하는 리스트 `parent` 활용
- `find`: 해당 노드의 루트 노드를 찾는 함수(재귀 활용)
- `union`: 두 노드의 루트 노드를 확인하고, 다른 경우 하나로 합치는 함수

```python
def solution(n, costs):
    answer = 0
    parent = [i for i in range(n)] # 부모 노드를 설정하기 위한 리스트
    costs.sort(key=lambda x:x[2]) # cost가 작은 값 기준으로 정렬

    def find(a): # 루트 노드를 찾는 함수
        if parent[a] == a: # 본인이 루트 노드인 경우
            return a
        parent[a] = find(parent[a])
        return parent[a] # 루트노드를 찾아 저장하고 리턴

    def union(a, b): # Tree 두개를 합치는 과정
        pa, pb = find(a), find(b) # 각 노드의 루트 노드
        if pa == pb : # 루트 노드가 같다는 것은 같은 트리
            return
        elif pa < pb : # 노드값이 더 낮은 트리쪽으로 합침
            parent[pb] = pa
        else :
            parent[pa] = pb
        return   

    for n1, n2, c in costs:
        if find(n1) != find(n2): # 루트 노드가 다르면 연결 후 경로 값 추가
            union(n1, n2)
            answer += c

    return answer
```





### 📌후기

---

kruskal 알고리즘이 무엇인지 배운 적이 있는데, 오랜 시간이 지나 사용하는 방법이나 활용하는 방법을 잊었었다. 이 문제를 통해 다시 한 번 이해할 수 있었고, kruskal 알고리즘과 관련된 내용을 정리해야겠다고 생각했다!