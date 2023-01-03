# My Naming Convetion
- since 2020
- new 2022.12
- 개인 프로젝트에서 네이밍 규칙 정리




## 함수
> camelCase로 작성
### API요청
- GET 요청
  - get + 취득할 데이터가 보관될 변수명
```js
예) 유저 목록 취득
const getUserList = () => {...}
```

- POST 요청
  - post + 작성할 데이터의 변수명
```js
예) 유저 객체 작성
const postUserObj = () => {...}
```

- Put 요청
  - put + 수정할 데이터의 변수명
```js
예) 유저 객체 수정
const putUserObj = () => {...}
```

- DELETE 요청
  - del + 삭제할 데이터의 변수명
```js
예) 유저 객체 삭제
const delUserObj = () => {...}
```

### 값의 변경 (DB값은 변경되지 않을때)
> API를 요청하기 전이나, View에서만 값의 작성, 수정, 삭제등이 일어날때(특히 Obj, Arr의 경우)
- 작성(Create)
  - add + 작성할 데이터의 변수명
```js
예) 유저 객체 작성
const addUserObj = () => {...}
```

- 수정(Update)
  - edit + 수정할 데이터의 변수명
```js
예) 유저 객체 수정
const editUserObj = () => {...}
```

- 삭제(DELETE)
  - rm + 삭제할 데이터의 변수명
```js
예) 유저 객체 삭제
const rmUserObj = () => {...}
```

### 이벤트
- 버튼 click 이벤트
  - 수행되는 함수의 내용 + btn
```js
예) 회원 가입 버튼을 클릭 했을때 유저 객체를 POST 하는 함수
const postUserObjBtn = () => {...}
```

- 이외의 이벤트
  - 수행되는 함수의 내용 + 이벤트명
```js
 작성중.......................
```

### Vue.js Mutation
### Vue.js Action






## CSS

## Vue Components


## 자주쓰는 단어 리스트
- 회원 : user
- 제품 : product
- 시리얼넘버 : srl
- 전화번호 : tel
- 휴대전화번호 : mobile
- 이메일 : email
- 우편번호 : zip
- 주소 : addr
- 상세주소 : addrDetail
- 회사, 업체 : company
