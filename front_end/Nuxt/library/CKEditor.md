# CKEditor.md
- 에디터 넣을 일이 생겨서 CKEditor를 Nuxt.js 프로젝트에 추가했다.

## Set Up
- nuxt.config.js에 플러그인으로 넣는 방법과 소개하려는 방법이 있다.
- nuxt.config.js에 plugin 등록하는건 제대로 동작을 잘 안하고.. 힌트를 얻을 소스를 구하기도 어렵기 때문에 조금 찝찝하더라도 일단 아래의 방법으로 추가하는게 정신건강에 이롭다.
- 기본 언어 설정하는 부분까지... 셋업 해봤다.

### CKEditor 패키지 설치
- 일단 아래 두개만 딱 설치해주면 된다.
```js
npm install @ckeditor/ckeditor5-vue2 --save
npm install @ckeditor/ckeditor5-build-classic --save
```

### CKEditor 임포트 및 뷰 스크립트
```js
let ClassicEditor, CKEditor

// 클라이언트 쪽에서만 임포트가 되야하기 때문에(window 객체에 접근이 필요함) 조건문 안에서 임포트 해야한다.
if (process.client) {
  require('@ckeditor/ckeditor5-build-classic/build/translations/ko') // 언어 설정을 하려면 꼭 임포트 시켜줘야한다.
  CKEditor = require('@ckeditor/ckeditor5-vue2') // 컴포넌트
  ClassicEditor = require('@ckeditor/ckeditor5-build-classic') // 에디터 객체
} else {
  CKEditor = { component: { template: '<div></div>' } }
}

export default {
  name: 'CkEditorIdx',
  components: {
    CkEditor: CKEditor.component, // 컴포넌트 사용을 위한 등록
  },
  data() {
    return {
      editor: ClassicEditor, // 에디터 객체를 담아둠
      editorConfig: {
        language: 'ko', // 한국어 옵션
      },
    }
  },
}
```

### CKEditor 템플릿
```vue
<div>
  <client-only> // 클라이언트에서만 로드 되게 하기 위함
    <CkEditor :editor="editor" :config="editorConfig"> // 스크립트에 정의해준 변수들을 각각 프로퍼티에 적용해준다.
    </CkEditor>
  </client-only>
</div>
```

### CKEditor 작성내용 데이터 취득하기
```vue
```

