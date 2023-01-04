
# Vue.js
> vue.js 관련 코드 컨벤션

## Vue 컴포넌트 내부 규칙
### data 내부에서 작성
  - 기본 변수명 컨벤션 앞에 "d_"를 붙여서 구분
  ```js
  // 예) 유저이름
  data: () => ({
    d_userName : String
  })
  ```
### props 내부에서 작성
  - 기본 변수명 컨벤션 앞에 "p_"를 붙여서 구분
  ```js
  // 예) 유저객체 prop
  props: {
    p_userObj: Object,
  }
  ```
### method 내부 작성

## Vuex 관련 규칙
### state
  - 기본 변수 명 컨벤션으로 작성
  ```
  // 예) 유저이름
  export const state = () => ({
    userName: '',
  })
  ```
- mutation
  - state 변수명 + Mut를 붙여서 작성
  - 값을 받는 파라미터는 다른 변수명을 지어주지 않고 payload로 통일한다.
  - mutation에는 값을 넣는 과정에 필요한 로직만 들어간다.
    > - api 요청 하지 않는다.
    > - 비즈니스 로직을 넣지 않는다.
    > - 다른 뷰를 호출하거나 라우팅 하지 않는다.
  - mutation 함수는 action에서만 호출한다.
    > - .vue 의 스크립트에서 mutation을 직접 호출하지 않고 항상 action을 통해서 호출한다.
  ```
  // 예) 유저이름
  export const mutations = {
    userNameMut(state, payload) {
      state.userName = payload
    },
  }
  // 예) Post요청을 하기 위해서 유저객체에 값을 추가하는 mutation
  export const mutations = {
    forPostUserObjMut(state, payload) {
      state.forPostUserObj = { ...state.forPostUserObj, ...payload }
    },
  }
  ```
- actions
  - state 변수명 + Act를 붙여서 작성
  -  ```
  // 예) 유저이름
  export const state = () => ({
    userName: '',
  })
  ```
