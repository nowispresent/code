# escape
- html 문자열을 서버로 보낼때 escape 처리
```js
cosnt htmlStr = '<p>some html string</p>'
const escapeHtml = escape(htmlStr) 
const unescapeHtml = unescape(escapeHtml)

console.log(escapeHtml) // %3Cp%3Esome%20html%20string%3C/p%3E
console.log(unescapeHtml) // <p>some html string</p>

```
