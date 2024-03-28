# 외판원 순회 2

## Stack

```python
def dfs_stack(graph, start): #node 하나만 탐색할거라면 함수 정의 안하기도 함
    visited = [False] * len(graph)
    stack = [(start, [start])] #최단 거리가 어떻게 되는지 필요한 경우 path배열 저장
    while stack:
        current_node, path = stack.pop()
        visitied[current_node] = True

        if len(path) == len(graph): #Base case: 모든 노드를 방문했을 때의 처리
            # 여기에서 최소 비용 계산 등을 수행할 수 있음
            # 최소 비용 계산 갱신, 최소 비용 path 갱신 등
            print("Complete path:", path)
            continue

        for next_node in range(len(graph[current_node])):
            if not visited[next_node] and graph[current_node][next_node] > 0: #->인접 행렬의 경우
            #인접 리스트-> if next_node in graph[current_node]:
                # 재귀 호출 대신 스택에 다음 방문 노드 추가
                stack.append((next_node, path + [next_node]))
    return # 최소 비용 경로 반환 등의 처리
```

- visited 관리가 약간 덜 직관적

## 재귀

```python
def dfs_recursive(graph, node, visited, path, paths):
    visited[node] = True
    path.append(node)

    # 모든 노드를 방문했으면, 경로와 현재까지의 비용을 저장
    if len(path) == len(graph):
        paths.append(list(path))
        # 비용 계산 로직을 여기에 추가할 수 있음
        # 예: path_cost = calculate_cost(path)
        # 최소 비용과 경로 업데이트 등
    else:
        # 아직 방문하지 않은 노드에 대해 재귀 호출
        for i, connected in enumerate(graph[node]):
            if connected and not visited[i]:
                dfs_recursive(graph, i, visited, path, paths)

    # 현재 노드의 방문을 취소하고 경로에서 제거하여 다른 경로 탐색 가능
    visited[node] = False
    path.pop()

def calculate_cost(path): # 헬퍼 함수
    # 경로의 비용을 계산하는 로직
    # 예시로, 단순 합계를 반환
    return sum(path)

# 그래프 예시 (인접 행렬)
graph = [[0, 1, 1, 1],
         [1, 0, 1, 1],
         [1, 1, 0, 1],
         [1, 1, 1, 0]]

# DFS 탐색 실행
start_node = 0
visited = [False] * len(graph)
paths = []
dfs_recursive(graph, start_node, visited, [], paths)

# 탐색된 모든 경로 출력
for path in paths:
    print(path)

```

- 직관적인 대신 함수에서 관리하는 매개변수가 길어진다는 단점

# 백트래킹
