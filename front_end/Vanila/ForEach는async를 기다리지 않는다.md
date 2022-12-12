# ForEach는 async를 기다리지 않는다.
- 참고한 페이지
[https://constructionsite.tistory.com/43](https://constructionsite.tistory.com/43)
[MDN Web Docs Array.prototype.forEach()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
- 위 블로그 글과 똑같은 상황이 생겨서 기록해둔다. 

## ForEach에서 async는 불가능
- ForEach 함수의 콜백이 비동기 함수였기 때문에, 호출이 끝난 뒤 부터 처리가 필요해서 async로 promise를 기다리는 처리를 했지만 되지 않았음.
- MDN에도 잘 설명되어 있다.
```
forEach() expects a synchronous function — it does not wait for promises. 
Make sure you are aware of the implications while using promises (or async functions) as forEach callbacks.

forEach()는 동기 함수를 기대합니다 — 약속을 기다리지 않습니다. forEach 콜백으로 약속(또는 비동기 함수)을 사용하는 동안 의미를 알고 있는지 확인하십시오.
```

## 대안
### for ~ of
- forEach 대신 for of를 사용해서 해결했다.
```js
  for (const [ index, chkVal ] of arr.entries()) {
    await awaitFunction({payload:{index : index, chk_val : chkVal})
  }
```
