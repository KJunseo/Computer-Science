## 깊이 우선 탐색(DFS)
그래프의 모든 정점을 발견하는 가장 단순하고 고전적인 방법

먼저 현재 정점과 인접한 간선들을 하나씩 검사하다가, 아직 방문하지 않은 정점으로 향하는 간선이 있다면 그 간선을 무조건 따라간다. 더 이상 갈 곳이 없다면 마지막에 따라갔던 간선을 따라 뒤로 돌아간다.

뒤로 돌아가는 것을 구현하기 위하여 거쳐온 정점들을 모두 저장해 둬야 한다. 이를 간편하게 하기 위해 재귀를 사용한다.(함수가 종료하면 호출한 위치로 되돌아가기 때문)

```
// 그래프의 인접 리스트 표현
vector<vector<int> > adj;

// 각 정점의 방문 여부
vector<bool> visited;

void dfs(int here) {
    cout << here << "\n";

    visited[here] = true; // 방문 여부 체크

    // 모든 인접 정점 순회 
    for(int i = 0; i < adj[here].size(); i++) {
        int there = adj[here][i];

        // 방문한 적이 없다면 방문 
        if(!visited[there]) dfs(there);
    }
}

// 그래프가 분리되어있는 경우를 만족시키기 위한 함수
void dfsAll() {

    visited = vector<bool>(adj.size(), false);

    for(int i = 0; i < adj.size(); i++) {
        if(!visited[i]) dfs(i);
    }
}
```
