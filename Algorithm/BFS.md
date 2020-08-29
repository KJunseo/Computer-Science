## 너비 우선 탐색(BFS)
시작점에서 가까운 정점부터 순서대로 방문하는 탐색 알고리즘

각 정점을 방문할 때마다 모든 인접 정점들을 검사. 
이 중 처음 보는 정점을 발견하면 이 정점을 방문 예정이라고 기록해 둔 뒤, 별도의 위치에 저장.
인접한 정점을 모두 검사하고 나면, 지금까지 저장한 목록에서 다음 정점을 꺼내어 방문.

즉 너비 우선 탐색의 방문 순서는 정점의 목록에서 어떤 정점을 먼저 꺼내는지에 의해 결정됨.

나중에 추가된 정점은 먼저 추가된 정점들이 전부 방문되기 전까지는 방문되면 안된다. -> 먼저 넣은 정점을 항상 먼저 꺼낸다. -> 큐를 사용

```
// 그래프의 인접 리스트 표현
vector<vector<int> > adj;

// start에서 시작해 그래프를 너비 우선 탐색하고 각 정점의 방문 순서를 반환
vector<int> bfs(int start) {
    // 각 정점의 방문 여부
    vector<bool> discovered(adj.size(), false);

    // 방문할 정점 목록을 유지하는 큐
    queue<int> q;

    // 정점의 방문 순서
    vector<int> order;

    discovered[start] = true; // 방문 처리
    q.push(start);

    while(!q.empty()) {
        int here = q.front();
        q.pop();

        // here를 방문
        order.push_back(here);

        // 모든 인접한 정점을 검사
        for(int i = 0; i < adj[here].size(); i++) {
            // 처음 보는 정점이면 방문 목록에 집어넣는다.
            if(!discovered[there]) {
                q.push(there);
                discovered[there] = true;
            }
        }
    }

    return order;
}
```

DFS와 달리 BFS는 발견과 방문이 같지 않다. 
모든 정점은 아래의 3개 상태를 순서대로 거쳐간다.
1. 아직 발견되지 않은 상태
2. 발견되었지만 아직 방문되지는 않은 상태(이 상태에 있는 정점들의 목록은 큐에 저장)
3. 방문된 상태 

**너비 우선 탐색은 그래프에서의 대개 최단 경로 문제를 풀 때만 사용된다.**