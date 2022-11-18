# copyToClipboard
- 텍스트를 클립보드에 복사하는 기능
- params
  - textArea : 복사에 사용할 textArea 엘리먼트를 넘겨준다
  - text : 복사할 내용(Stirng)을 넘겨준다.
```js
export const copyData = (textArea, text) => {
  textArea.value = text;
  textArea.style.visibility = "visible";
  textArea.select();
  document.execCommand("copy");
  textArea.style.visibility = "hidden";
};
```
