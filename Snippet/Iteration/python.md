# 배열

```python
arr = [1,3,2]
## 반복문
for v in arr:
  print(v)

## 반복문 with index
for i,v in enumerate(arr):
  print(i,v)
```

# Object

```python
my_dict = {'a': 1, 'b': 2, 'c': 3}

#키만 순회
for key in my_dict:
    print(key)  # a, b, c

# 값만 순회
for value in my_dict.values():
    print(value)  # 1, 2, 3

# 키와 값 함께 순회
for key, value in my_dict.items():
    print(key, value)  # ('a', 1), ('b', 2), ('c', 3)

```

# 고급

- Generator 만들기 (yield)
- [Generator의 장.단점]()

```python
def num_generator():
  yield 0
  yield 1
  yield 2

for i in nmuber_generator():
  print(i)
```
