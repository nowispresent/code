# [ERROR] The client-side rendered virtual DOM tree is not matching server-rendered content.

## 원인
- v-if 조건으로 화면을 표시할지 안할지 결정하는 로직에서 발생,
- 해당 v-if 조건의 결정은 beforeMount()에서 수행했음
- v-if 조건을 사용하게 되면 돔 자체를 그리지 않아서 문제가 발생했다고 판단.

## 해결
- v-if 조건을 v-show로 변경.
