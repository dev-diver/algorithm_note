# 큐

```python
from collections import deque
que = deque()
# que = deque([])
# que = deque([1,2,3])
que.append(1)
que.popleft()
```

# 깊은 복사

```python
import copy
arr = [[1,2,3],[3,2,1]]
arr2 = copy.deepcopy(arr)
```

# 힙

```python
import heapq  #기본적으로 최소힙
heap = []
heapq.heappush(heap, 4)
smallest = heapq.heappop(heap)
smallest = heap[0]

mylist = [4,1,7,3,5]
heapq.heapify(mylist) #시간 복잡도 O(n)
```

# 순열, 조합

```python
from itertools import permutations
a=[1,2,3]
perm = permutations(a,2) #[(1,2),(1,3),(2,1),(2,3),(3,1),(3,2)]

from itertools import combinations
combi = combinations(a,2) #[(1,2),(1,3),(2,3)]

```
