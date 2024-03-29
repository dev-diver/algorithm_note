# DFS - 스택과 재귀 장단점 비교

## 재귀

- 장
  - 직관적이다.
  - 특히 전위 처리, 후위 처리가 직관적이다.
  - 내부 구조가 조금 더 짧다.
- 단
  - 매개변수가 늘어난다.(pop 과 함께 나오는 값 전체 넘겨줘야 함)
  - 재귀 깊이가 깊어지면서 recursive_limit에 걸리기도 한다.

## 스택

- 장
  - 매개변수가 적다.
  - 스택에 넣고 뺄 값들을 직접 컨트롤 할 수 있다.
  - 재귀 깊이 컨트롤에도 관여 가능하다.
- 단
  - pop(), append()를 직접 해줘야 한다.
  - 전위처리, 후위 처리는 따로 해줘야 한다.

## 전위처리, 후위처리

### 재귀

```python
def dfs(node):
  if base_case:
    # 베이스 케이스 처리
    return base_result
  #전위 처리
  for next_node in next_nodes:
    dfs(next_node)
  #후위 처리
dfs(start_node)

```

### 스택

```python
while stack:
    node, state = stack.pop()
    if state == 'pre':
        # 전위 처리
        if base_case:
            # 베이스 케이스 처리
            continue
        # 후위 처리를 위해 현재 노드를 다시 스택에 추가
        stack.append((node, 'post'))
        # 자식 노드들을 스택에 추가
        for next_node in next_nodes:
            if not visited[next_node]:
                stack.append((next_node, 'pre'))
    else:
        # 후위 처리 로직
        pass
```
