# 코드

```python
def bellman_ford(graph, start_vertex):
    # 거리 값을 저장할 딕셔너리, 모든 정점을 무한대로 초기화
    distances = {vertex: float('infinity') for vertex in graph}
    distances[start_vertex] = 0  # 시작 정점의 거리는 0으로 초기화

    #1.메인 V-1번 반복(V는 정점 수)
    for _ in range(len(graph) - 1):
        for vertex in graph:
            for neighbor in graph[vertex]:
                #Relax. 만약 현재 정점을 경유하는 것이 더 짧은 경로라면 거리를 갱신
                if distances[vertex] + graph[vertex][neighbor] < distances[neighbor]:
                    distances[neighbor] = distances[vertex] + graph[vertex][neighbor]

    #2.음의 사이클 체크. 체크 필요 없을시 없어도 됨
    for vertex in graph:
        for neighbor in graph[vertex]:
            if distances[vertex] + graph[vertex][neighbor] < distances[neighbor]:
                print("Graph contains a negative weight cycle")
                return None

    return distances

# 그래프는 인접 리스트로 표현, 각 정점에서 연결된 정점과 가중치 정보 포함
graph = {
    'A': {'B': 1, 'C': 4},
    'B': {'C': 3, 'D': 2, 'E': 2},
    'C': {},
    'D': {'B': 1, 'C': 5},
    'E': {'D': -3}
}

start_vertex = 'A'
distances = bellman_ford(graph, start_vertex)
```
