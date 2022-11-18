# Regex.md
- 자주 쓰는 정규식을 모아둔 모듈 계속적으로 업데이트 예정

```js
/** 정규식 및 포맷 regex **/
//숫자만 입력 허용
export const regexNum = /[^0-9]/g;

//영문, 숫자, 한글 및 천지인 키보드 입력(ㆍᆢ) 특수문자 ()., 허용
export const regexEnKrNum = /[^ㆍᆢ().,|a-z|A-Z|0-9|ㄱ-ㅎ|가-힣\s]/g;

//사업자번호 정규식
export const regexBizNum = /^(\d{3})(\d{2})(\d{5})$/;
//사업자번호에 하이픈 넣기
export const formatBizNum = (str) => {
  return str.replace(regexBizNum, `$1-$2-$3`);
};

//휴대전화번호 정규식
export const regexPhone = /^(\d{3})(\d{3,4})(\d{4})$/;
//휴대전화번호 정규식에 하이픈 넣기
export const formatPhoneNum = (str) => {
  return str.replace(regexPhone, `$1-$2-$3`);
};

//유선전화번호 정규식
export const regexTel = /^(\d{2,3})(\d{3,4})(\d{4})$/;
//휴대전화번호 정규식에 하이픈 넣기
export const formatTelNum = (str) => {
  return str.replace(regexTel, `$1-$2-$3`);
};
```
