# ChangeArrayOrder.js
- 배열의 순서를 바꾸는 로직
- param
  - list : 순서 변경을 수행 할 배열
  - targetPosition : 변경 할 요소의 현재 위치 인덱스(int)
  - position : 변경 할 요소를 얼마나 이동할지(예 : 2칸, -2칸)(int)
- return
  - tempList : 순서 변경이 끝난 배열(arr)
```js
export const ChangeArrayOrder = (list, targetPosition, position) => {
  // 이동할 요소(target)의 index값, 얼마나 이동할지(position)값을 더해서 저장해둠
  const newPosition = targetPosition - 1
  
  // 만약 새로 이동하는 위치가 0보다 작거나 전체 배열 길이보다 크면 수행하지 않음
  if (newPosition < 0 || newPosition >= list.length) return
  
  // 이동 수행을 위해서 원본 리스트를 복사
  const tempList = list
  
  // 복사한 리스트에서 타겟을 제거하고, 새로운 변수에 따로 저장해둠
  const target = tempList.splice(targetPosition, 1)[0]
  
  // 위에서 저장한 이동할 위치값에 따로 저장해둔 타겟을 삽입해준다.
  tempList.splice(newPosition, 0, target)
  
  return tempList
};

```
