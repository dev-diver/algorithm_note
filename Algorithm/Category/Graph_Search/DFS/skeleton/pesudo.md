# 기본

- [고찰 - 스택과 재귀 장단점 비교](./discussion1.md)
- ex&#41; [프-타겟넘버](https://school.programmers.co.kr/learn/courses/30/lessons/43165)

## Stack

```python
stack = []
stack.push(start_node)
while stack:
  node = stack.pop()
  if base_case:
    # 베이스케이스 처리
    continue
  # 방문시 처리
  for next_node in next_nodes:
    stack.push(next_node)
```

## Recursion

```python
def dfs(node):
  if base_case:
    # base_case 처리
    return
  # 방문시 처리
  for next_node in next_nodes:
    dfs(next_node)

dfs(start_node)
```

# 그래프(재방문 안하기)

- [고찰 - visit처리 위치](./discussion2.md)

## Stack

```python
stack=[]
visited=[False]*N #노드 수
stack.push(start_node)
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

## Recursion

```python
visited = [False]*N #노드 수
def dfs(node, visited):
  if visited[node]:
    return visit_result
  visited[node] = True
  # 방문시 처리
  if base_case:
    # 베이스 케이스 처리
    return base_result

  #전위 처리
  for next_node in next_nodes:
    dfs(next_node, visited)
  #후위 처리

dfs(start_node)
```
