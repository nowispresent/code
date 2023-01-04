# 배열 관련 함수
## 정렬(sort)
> Array.sort(()=>{})

- 기본사용
```
// 예)
const arr = targetArr.sort((a,b) => a-b);
```

- 배열의 요소가 객체이고 객체의 요소로 정렬
```
// 예)
const arr = targetArr.sort((a,b) => a.sort_val - b.sort_val);
```
 
