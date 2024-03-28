# 전역변수

- `global` 다른 함수 스코프에서 재할당 하려면 global로 미리 선언이 되어있어야 한다.
- 그렇지 않으면 지역 변수가 생기고 덮어씌워짐

## 예제

```python
x = 0  # 전역 변수

def increment():
    global x  # 전역 변수 x를 수정하기 위해 global 키워드 사용
    x += 1

```
