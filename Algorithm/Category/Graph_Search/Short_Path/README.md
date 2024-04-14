- 벨만-포드 : One to All shortest
- 다익스트라 : One to All shortest
- 플로이드 워셜 : All to All shortest

# 특징

## 벨만-포드

- 시간복잡도: O(VE)
- 알고리즘 분류 : DP
- 그래프 특징
  - 가중치가 있는 그래프
  - 가중치가 음수여도 됨
  - 음의 사이클이 있는 경우 감지 가능
  - 방향, 무방향 모두 적용 가능

## 다익스트라

- 시간복잡도: O((V+E)logV)
- 알고리즘 분류 : 그리디
- 그래프 특징
  - 가중치가 있는 그래프
  - 모든 가중치는 양수여야 함
  - 방향, 무방향 모두 적용 가능

## 플로이드 워셜

- 시간복잡도: O(V^3). All to All이라는데 주목
- 알고리즘 분류 : DP
- 그래프 특징
  - 가중치가 있는 그래프
  - 음의 가중치 가능
  - 음의 사이클은 있으면 안 됨
  - 방향, 무방향 적용 가능 (주로 방향)
  - 인접 행렬 그래프가 구현이 편함

## 벨만 포드 VS 플로이드 워셜

- 벨만포드 - 모든 엣지에 대해 Vertex 만큼 반복 O(VE)
- 플로이드 워셜 - 모든 Vertex간 관계에 대해 Vertex만큼 반복 O(V^3)
- One to All 만 필요한 경우. O(VE) 가 O(V^3)보다 빠르므로 벨만 포드