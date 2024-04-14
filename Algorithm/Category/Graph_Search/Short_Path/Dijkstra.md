# 코드

```python
import heapq
import sys

def dijkstra(graph, start):
    # 거리 정보를 저장할 딕셔너리, 모든 거리는 무한대로 초기화
    distances = {vertex: float('infinity') for vertex in graph}
    distances[start] = 0  # 시작 정점의 거리는 0
    # 모든 정점을 우선순위 큐에 넣음
    priority_queue = [(0, start)]

    while priority_queue:
        # 우선순위 큐에서 거리가 가장 짧은 정점을 pop
        current_distance, current_vertex = heapq.heappop(priority_queue)

        # 현재 정점의 거리 정보가 우선순위 큐에 있는 거리보다 작으면 이미 처리된 것
        if current_distance > distances[current_vertex]:
            continue

        # 인접한 정점들의 거리를 확인하고 업데이트
        for neighbor, weight in graph[current_vertex].items():
            distance = current_distance + weight

            #Relax. 만약 새로 계산한 거리가 기존 거리보다 작으면 갱신
            if distance < distances[neighbor]:
                distances[neighbor] = distance
                # 갱신된 거리 정보를 우선순위 큐에 넣음
                heapq.heappush(priority_queue, (distance, neighbor))

    return distances

# 그래프는 딕셔너리로 표현, 각 정점에서 인접한 정점으로의 가중치 정보 포함
graph = {
    'A': {'B': 1, 'C': 4},
    'B': {'A': 1, 'C': 2, 'D': 5},
    'C': {'A': 4, 'B': 2, 'D': 1},
    'D': {'B': 5, 'C': 1}
}

start_vertex = 'A'
distances = dijkstra(graph, start_vertex)
```
