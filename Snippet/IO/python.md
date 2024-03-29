# 입력

## 배열

```python
import sys
input = sys.stdin.input

#정수 한 개
N = int(input())

#정수 한 줄에 여러개
numbers = [*map(int, input().split())]

#정수 N 줄에 한개씩
lines = [int(input()) for _ in range(N)]

#정수 N 줄에 여러개 (2중 배열)
M = [[*map(int, input().split())] _ for range(N)]

tup = map(int, input().split())  #튜플은 배열로 안 만들어도 됨
```

# 출력

```python
print(N)

#배열 띄어쓰기로 출력
print(*arr)

#배열 여러 줄로 출력
print(*arr, sep='\n')

#맵 띄어쓰기, 여러줄로 출력
for line in M:
  print(*line)
# 최적화
print(*[' '.join([*map(str,line)]) for line in M], sep='\n')

```

## TODO

- 인접 행렬
- 인접 리스트
