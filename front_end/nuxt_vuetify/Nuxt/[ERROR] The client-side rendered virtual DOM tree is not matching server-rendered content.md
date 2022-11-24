# [err] The client-side rendered virtual DOM tree is not matching server-rendered content.

## 원인
- v-if로 화면을 표시할지 안할지 결정하는 로직에서 발생,
- 해당 v-if 조건의 결정은 beforeMount()에서 수행했음
- v-if를 사용하게 되면 돔 자체를 그리지 않아서 문제가 발생했다고 판단.

## 해결
- v-if를 v-show로 변경.
- v-show는 hidden 하는 효과이기 때문에 돔트리에 차이가 발생하지 않는다.
