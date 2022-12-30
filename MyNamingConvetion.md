# My Naming Convetion
- since 2020
- new 2022.12
- 개인 프로젝트에서 네이밍 규칙 정리

## 변수
> camelCase로 작성
### 상태값(State)
- String
  - 명사
```
예) 유저 이름
=> userName
```

- Number
  - 명사 + Num
```
예) 회원 전화번호 (String)
=> userTel

예) 회원 전화번호 (Number)
=> userTelNum
```

- Boolean
  - is + "true 조건"을 의미하는 동사 또는 명사
```
예) 다크모드일때 "true"를 갖는 상태 변수일 경우
=> isDarkMode
```

- List
- 명사 + List
```
예) 회원 객체를 담고있는 배열
=> userList
```
- Object
- 명사 + Obj
```
예) 회원 객체
=> userObj
```

### Vue.js
> .vue 파일 내부에서 정의했을때 규칙
- data 안에서 정의
  - 변수명 앞에 "d_"를 붙여서 구분
  ```js
  // 예) 유저이름
  data: () => ({
    d_userName : String
  })
  ```
- props 정의
  - 변수명 앞에 "p_"를 붙여서 구분
  ```js
  // 예) 유저객체 prop
  props: {
    p_userObj: Object,
  }
  ```

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
