# getDataFromObj
- 오브젝트 배열에서 필요한 값만 추출하는 방법에 관해서.

## map
- 원하는 값만 빼서 배열로 출력하기
- map을 사용하면 배열 내부 오브젝트의 원하는 값만 추출한 배열 값을 리턴받을 수 있다.
```js
const arr = [
      { key: '1', value: 'james' },
      { key: '2', value: 'lars' },
      { key: '3', value: 'robert' },
      { key: '4', value: 'kirk' },
    ]
const getValueFromObjArr = arr.map((row) => row.value)
console.log(getValueFromObjArr)
//result
//["james", "lars", "robert", "kirk"]
```

## map + rest param
- 제외하고 싶은 값만 빼서 배열로 출력하기
- rest parameter를 사용해서 제외하고 싶은 값만 빼낼수 있다.
```js
const arr = [
      { key: '1', value: 'james', part: 'guitar&vocal' },
      { key: '2', value: 'lars', part: 'drums' },
      { key: '3', value: 'robert', part: 'bass' },
      { key: '4', value: 'kirk', part: 'guitar' },
    ]
const getExceptValueFromObjArr = arr.map(({ key, ...rest }) => rest)
console.log(getExceptValueFromObjArr)

//result
//(4) [{…}, {…}, {…}, {…}]
//0: {value: 'james', part: 'guitar&vocal'}
//1: {value: 'lars', part: 'drums'}
//2: {value: 'robert', part: 'bass'}
//3: {value: 'kirk', part: 'guitar'}
```
