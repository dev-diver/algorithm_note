## 배열 최대값

```javascript
const arr = [1, 3, 2];

//최대값 구하기
const max_val = Math.max(...arr);

//인덱스 최대까지 구하기
const max_tuple = arr.reduce(
  (acc, val, idx) => (val > acc.val ? { idx, val } : acc),
  { idx: -1, val: -Infinity }
);
```
