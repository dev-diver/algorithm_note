# DFS Visit 처리 위치

## pop 하면서 처리

```python
while stack:
  node = stack.pop()
  if visited[node]:
    continue
  visited[node]=True
  # 방문시 처리
  if base_case:
    #베이스 케이스 처리
    continue

  for next_node in next_nodes:
    stack.push(next_node)

```

## push 하면서 처리

```python
while stack:
  node = stack.pop()
  # 방문시 처리
  if base_case:
    #베이스 케이스 처리
    continue

  for next_node in next_nodes:
    if(visited[next_node]):
      visited[next_node]=True
      stack.push(next_node)

```

## 장단 점 비교 - 직관과 성능의 Trade off

### pop 근처

- 장점
  - 직관적 구현
- 단점
  - 불필요한 노드 추가 : 스택이 필요 이상으로 길어짐

### push 근처

- 장점:
  - 스택 메모리 절약 : 불필요한 노드를 추가하지 않음
- 단점:
  - 구현 직관성 떨어짐 : 방문 체크 로직이 노드 처리 로직과 분리되어 있어 코드의 가독성이 다소 떨어짐.
