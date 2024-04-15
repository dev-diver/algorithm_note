# Set

```python
S=set()
S.add('a')
S.remove('a')
S.discard('a') #요소가 없어도 exception 안남

#응용
A=set()
B=set()
C=A&B # 교집합
C=A|B # 합집합
C=A-B # 차집합

S = {'a'}  # 바로 set를 만들 수 있음.
S = {} # 주의. 이렇게 하면 집합이 아닌 딕셔너리가 만들어져버림
```

# Map

```python
d = dict()
d = {} # 인터프리터가 더 빠르게 해석함

d['a'] = b # 삽입
del d['a'] # 삭제
val = d.pop('b', 기본값) # keyError없이 삭제.(key가 없는 경우 기본값이 나옴)

val = d['a'] # 값 접근
val = d.get('a', 기본값) # keyError 없이 접근

#응용
d['a'] = d.get('a',0) + 1 #누적합시 좋음
```
