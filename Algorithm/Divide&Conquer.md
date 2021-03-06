## 분할 정복(Divide & Conquer)

주어진 문제를 둘 이상의 부분 문제로 나눈 뒤 각 문제에 대한 답을 재귀 호출을 이용해 계산하고, 각 부분 문제의 답으로부터 전체 문제의 답을 계산해내는 것

**문제를 한 조각과 나머지 전체로 나누는 대신 거의 같은 크기의 부분 문제로 나누는 것**

### 분할 정복의 구성 요소
1. 문제를 더 작은 문제로 분할(Divide)
2. 각 문제에 대해 구한 답을 원래 문제에 대한 답으로 병합(Merge)
3. 답을 더이상 분할하지 않고 풀 수 있는 가장 작은 문제(Base case)

**분할 정복은 같은 작업을 더 빠르게 할 수 있게 해준다**

### 분할 정복을 사용한 알고리즘 예시
- 퀵 정렬[퀵 정렬](/Algorithm/Quick_sort.md)
- 병합 정렬[병합 정렬](/Algorithm/Merge_sort.md)

퀵 정렬과 병합 정렬을 둘 다 분할 정복을 사용한 알고리즘이지만, 퀵 정렬은 분할 단계에서 시간이 많이 걸리고 병합 정렬은 병합 단계에서 시간이 많이 걸린다는 차이가 있다.