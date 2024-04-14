# 문제

[케빈 베이컨의 6단계 법칙](https://www.acmicpc.net/problem/1389)

# 코드

```python
def floyd_warshall(graph):
    # 정점의 개수
    num_vertices = len(graph)
    # 거리 행렬 초기화
    dist = [[float('inf')] * num_vertices for _ in range(num_vertices)]

    # 자기 자신으로의 거리는 0
    for i in range(num_vertices):
        dist[i][i] = 0

    # 각 간선에 대해 거리 행렬 초기화
    for i in range(num_vertices):
        for j in range(num_vertices):
            if graph[i][j] is not None:
                dist[i][j] = graph[i][j]

    # 플로이드-워셜 알고리즘 적용
    for k in range(num_vertices):
        for i in range(num_vertices):
            for j in range(num_vertices):
                #Relax
                if dist[i][j] > dist[i][k] + dist[k][j]:
                    dist[i][j] = dist[i][k] + dist[k][j]

    return dist

# 그래프는 인접 행렬 형식으로 제공
# None은 두 정점 사이에 직접적인 경로가 없음을 의미
graph = [
    [None, 3, None, None, None, None],
    [3, None, 1, None, None, None],
    [None, 1, None, 7, None, None],
    [None, None, 7, None, 2, 8],
    [None, None, None, 2, None, 4],
    [None, None, None, 8, 4, None]
]

# 정점간의 거리를 None 대신 무한대로 초기화
for i in range(len(graph)):
    for j in range(len(graph)):
        if graph[i][j] is None:
            graph[i][j] = float('inf')

# 알고리즘 실행
distances = floyd_warshall(graph)
```
