## Graph(그래프)

노드와 간선을 하나로 모아놓은 비선형 자료구조이다.
방향 그래프와 무방향 그래프로 나뉜다.

- vertex(정점): 트리의 노드와 같은 의미이다.
- edge(간선): 각 정점을 연결하는 선이다.
- adjacent vertex(인접 정점): 간선에 의해 직접 연결된 정점이다.
- degree(차수): 무방향 그래프에서 하나의 정점에 인접한 다른 정점의 수이다.
- in-degree(진입 차수): 방향 그래프에서 외부에서 오는 간선의 수이다.
- out-degree(진출 차수): 방향 그래프에서 외부로 향하는 간선의 수이다.
- simple path(단순 경로): 경로 중에서 반복되는 정점이 없는 경우이다.
- cycle(싸이클): 단순 경로의 시작 정점과 끝 정점이 동일한 경우이다.

트리와 달리 루트 노드라는 개념이 없으며, 부모-자식 이라는 개념도 없다.

### 무방향 그래프
간선을 통해 양 방향으로 갈 수 있다.
A-B와 B-A가 동일하다.

### 방향 그래프
간선에 방향이 존재하므로 정해진 방향으로만 갈 수 있다.
A->B 와 A<-B는 다르다.

### 가중치 그래프
간선에 비용 값이 할당되어 있는 그래프를 뜻한다.

### 연결 그래프
무방향 그래프에 있는 모든 정점쌍에 대해 항상 경로가 존재하는 경우이다.

### 비연결 그래프
무방향 그래프에서 경로가 존재하지 않는 정점쌍이 있는 경우이다.

### 완전 그래프
그래프에 속한 모든 정점쌍이 서로 연결되어 있는 경우이다.

### 구현 방법
1. Adjacency List(인접 리스트)
각 정점을 기준으로 인접한 정점들을 리스트로 표시하는 방법
적은 숫자의 간선을 가지는 경우 사용한다.

2. Adjacency Matrix(인접 행렬)
N x N 배열로 연결을 나타내며 matrix[i][j]는 i->j의 연결상태를 나타낸다.
많은 숫자의 간선을 가지는 경우 사용한다.