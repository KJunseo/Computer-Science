## Heap(힙)

완전 이진 트리의 일종이며 [우선 순위 큐](/DataStructure/Stack&Queue.md#Priority-Queue(우선-순위-큐))를 위해 만들어졌다.

일반적으로 배열을 사용해서 구현한다.(루트 노드 인덱스를 0이 아닌 1로 하면 구현이 편하다)
여러 값들 중 최대값이나 최솟값을 빠르게 찾아내도록 만들어졌다.
반 정렬 상태를 유지하고 있으며 중복된 값을 허용한다.(노드의 대소 관계는 부모-자식 노드 간에만 적용되며 형제들 사이에는 정해지지 않는다.)

### max heap(최대 힙)
부모 노드의 값이 자식 노드의 값보다 크거나 같은 완전 이진트리이다. 루트의 값이 가장 크므로 최대값을 찾을 때 O(1)이다. 

하지만 만약 최대값을 제거하는 경우 루트노드를 대체할 다른 노드를 찾아야하는데 이 때 맨 마지막 노드를 루트 노드로 대체시킨 후 heap 구조를 맞추기 때문에 이 경우는 O(log n)이 된다.

### min heap(최소 힙)
부모 노드의 값이 자식 노드의 값보다 작거나 같은 완전 이진트리이다. 루트의 값이 가장 작으므로 최솟값을 찾을 때 O(1)이다.

하지만 만약 최솟값을 제거하는 경우 루트노드를 대체할 다른 노드를 찾아야하는데 이 때 맨 마지막 노드를 루트 노드로 대체시킨 후 heap 구조를 맞추기 때문에 이 경우는 O(log n)이 된다.