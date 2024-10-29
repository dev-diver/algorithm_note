# 슬라이스

```go
A = []int{1,2,3}

for i := range A {
    // 하나만 쓰면 v가 아니라 i임에 유의
}

for _, v := range A {
    
}

for idx, val := range A {

}
```

# 배열
```go
A := [3]int{1,2,3}
A := [...]int{1,2,3}

//위의 반복문이 배열에도 똑같이 적용됨
```

# Object
* python보다 직관적
* 순서는 보장되지 않는다.
```go
myDict := map[string]int{
    "a" : 1,
    "b" : 2,
    "c" : 3   
}

for key := range myDict{
    //value가 아니라 key임에 유의
}

for _, val := range myDict{

}

for key,val := range myDict{

}

```