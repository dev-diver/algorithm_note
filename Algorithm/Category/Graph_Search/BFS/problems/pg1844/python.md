```python
import copy
from collections import deque
def solution(maps):
    que = deque([])
    que.append(((0,0),1))

    maxX = len(maps)-1
    maxY = len(maps[0])-1
    maxM = maxX * maxY
    direction = [(1,0),(-1,0),(0,1),(0,-1)]

    while que:

        (x, y), move = que.popleft()
        if(x == maxX and y == maxY):
            return move

        for mx,my in direction:
            nx,ny = x+mx, y+my
            if(0 <= nx <= maxX and 0 <= ny <= maxY and maps[nx][ny] != 0):
                que.append(((nx,ny),move+1))
                maps[nx][ny] = 0

    return -1
```
