## 병합 정렬(Merge Sort)

주어진 순열을 가운데에서 쪼개 비슷한 크기의 수열 두 개로 만든 후, 이들을 재귀 호출을 이용해 각각 정렬하고 정렬된 배열을 하나로 합쳐서 정렬된 전체 수열을 얻는 방법

### 병합 정렬 과정 
각 수열의 크기가 1이 될 때까지 절반씩 쪼개 나간 뒤 부분 배열들을 합치면서 정렬한다.

절반씩 쪼갤 때는 O(1)이 걸리지만 합칠 때 O(n)이 걸린다. 

### 시간 복잡도
정렬된 두 부분 수열을 합칠 때 두 수열의 길이 합만큼 반복문을 수행해야한다.

아래 단계로 갈수록 부분 문제의 수는 두 배로 늘고, 각 부분 문제의 크기는 반으로 줄어들기 때문에 한 단계 내에서 병합에 필요한 시간은 O(n)으로 동일하다. 

따라서 단계의 수에 n을 곱하면 병합 정렬에 필요한 전체시간을 알 수 있다. 

문제의 크기는 거의 항상 절반으로 나누어지므로 필요한 단계의 수는 O(lgn)이 된다. 

즉, 병합정렬의 시간복잡도는 O(nlgn)이다. 