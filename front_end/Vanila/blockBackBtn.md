# blockBackBtn
- 브라우저에서 뒤로가기 버튼 또는 안드로이드 백버튼을 수행을 막는 방법
- 모달이 열리고 나서 뒤로가기 눌렀을 때, 이전페이지로 전환되는 현상을 막을 때 사용하고 있음

## 1. 백버튼(뒤로가기)를 수행한 뒤에 실행할 함수 정의
```js
preventBackPage() {
  // 히스토리로 이동하지 않고 어디로 이동 시킬지 정해 줌
	this.$router.push("/", () => {});
  // 수행한 뒤에 뒤로가기 등록된 이벤트를 없애줌
	window.removeEventListener("popstate", this.preventBackPage);
},
```

## 2. 백버튼을 막아야하는 시점에 이벤트를 추가 해줌
```js
window.addEventListener("popstate", this.preventBackPage);
```

## 3. 백버튼을 막아야하는 시점에서 벗어나면 이벤트를 해제 해줌

```js
- 모달 닫히는 시점에 뒤로가기 막는 이벤트 해제
window.removeEventListener("popstate", this.preventBackPage);
```
