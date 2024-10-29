# Map

```go
myDict := map[string]int{}
myDict := make(map[string]int)
//용량을 미리 설정해 cap을 넘기 전가지 메모리 할당 시간을 절약할 수 있다.
myDict := make(map[string]int, 10)


//삽입
myDict["a"] = b

//삭제.  없는 값을 삭제해도 runtime에러 안 남
delete(myDict, "a")

//값 접근
val, exist := myDict  // 값이 없을 때 val은 기본값을 반환함.

//응용
myDict["a"] += 1 // defaultDict처럼 오류없이 누적
```

# Set

```go
//첫번째 방법
s := make(map[string]bool) // 존재 여부만 표시. 세트로만 쓸 때는 이게 더 좋음

s["a"] = true
delete(s, "a") //혹은
s["a"] = false

//두번째 방법
s := make(map[string]interface{}) // 만약의 경우에 값 추가 가능
s["a"] = interface{}{}

delete(s, "a")
```

# Set 만들기!
```go
type Set[T comparable] map[T]bool

func set[T comparable](slice []T) Set[T] {
    resultSet := make(Set[T])
    for _, v := range slice {
        resultSet[v] = true
    }
    return resultSet
}

slice := []int{1,2,3}
s := set(slice)
```

* int 형이랑 interface{} 형이랑 다름에 주의해야 한다. -> 제너릭을 사용한다.