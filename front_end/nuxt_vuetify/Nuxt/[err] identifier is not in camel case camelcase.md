# identifier is not in camel case camelcase
- 카멜케이스로 작성하지 않았을때 NUXT에서 던지는 ESLINT에러
- 카멜케이스로 맞춰서 작성하면 좋겠지만 급하게 테스트 할게 있을때는 옵션을 잠시 끄고 작업할 필요가 가끔 있음.

## 설정
- eslintrc.js
```js
module.exports = {
  ...
  rules: { camelcase: ['error', { properties: 'never' }], camelcase: 'off' },
  ...
}
```
- 옵션을 넣어주니 이상없이 잘 동작한다.


## 옵션 설명
```js
camelcase: ['error', { properties: 'never' }]
```
- 카멜케이스로 작성하지 않았을때 에러페이지를 띄우지 않게 함
```js
camelcase: 'off' 
```
- 에디터 안에서 카멜케이스로 작성하지 않은 부분을 하이라이트 하지 않게 함.
