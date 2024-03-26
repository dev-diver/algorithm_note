# 배열

```javascript
const arr = [1, 3, 2];

// 반복문
for (const v of arr) {
  console.log(v);
}

// 반복문 index
for (let i = 0; i < arr.length; i++) {
  console.log(i);
}

// 반복문 with index
for (const [index, element] of arr.entries()) {
  console.log(index);
}

// 반복문 with index 함수형
arr.forEach((v, i) => {
  console.log(i, v);
});

//index 순회 아래도 가능하지만 원치않는 요소를 순회할 위험
for (const i in arr) {
  console.log(i);
}
```

# Object

## for문

```javascript
let myObj = { a: 1, b: 2, c: 3 };

//키만 순회
for (const key of Object.keys(myObj)) {
  console.log(key); // a, b, c
}

// 값만 순회
for (const val of Object.values(myObj)) {
  console.log(val);
}

//키와 값 함께 순회
for (const [key, value] of Object.entries(myObj)) {
  console.log(key, value); // a 1, b 2, c 3
}

//참고
//key 순회
for (const key in myObj) {
  //상속시 프로토타입 체인 키값도 순회할 위험 있음
  console.log(key); // a, b, c
}

//값 순회. 이건 안됨
for (const val of myObj) {
  //Object는 기본적으로 Iterable이 아님.
  console.log(val);
}
```

## 함수형

```javascript
//키만 순회
Object.keys(myObj).forEach((key) => {
  console.log(key);
});

// 값만 순회
Object.values(myObj).forEach((value) => {
  console.log(value); // 1, 2, 3
});

// 키와 값 함께 순회
Object.entries(myObj).forEach(([key, value]) => {
  //구조 분해 할당
  console.log(key, value); // a 1, b 2, c 3
});
```
