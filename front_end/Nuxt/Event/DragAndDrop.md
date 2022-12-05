# Drag and Drop
- Vue에서 드래그앤 드롭 구현에 사용하는 함수
- 액션뒤에 .prevent(e.preventDefault()와 같은 역할)키워드를 붙여서 액션 중복 등을 막아야 제대로 작동하는 경우가 있음.

## draggable = true
- 드래그 대상으로 지정하기
```vue
<div :draggable = "true" >드래그 할 대상 영역</div>
```

## dragstart
- 드래그 시작 이벤트, 드래그 대상으로 지정된 엘리먼트를 press down 하면 동작함
```vue
<script>
  ...
  methods:{
    func_dragStart(){
      console.log("드래그 시작")
    }
  }
  ...
</script>

<template>
  <div @dragstart = "func_dragStart">드래그 할 대상 영역</div>
<template>
```

## dragover
- 드래그를 놓을 대상에게 커서가 접근했을 때의 이벤트
```vue
<script>
  ...
  methods:{
    func_dragOver(){
      console.log("드래그 접근")
    }
  }
  ...
</script>

<template>
  <div @dragover.prevent = "func_dragOver">드래그 놓을 대상 영역</div>
<template>
```

## dragleave
- 드래그를 놓을 대상에게 커서가 접근했다가 놓지 않고 다시 영역 밖으로 나갔을때
```vue
<script>
  ...
  methods:{
    func_dragLeave(){
      console.log("드래그 나감")
    }
  }
  ...
</script>

<template>
  <div @dragleave.prevent = "func_dragLeave">드래그 놓을 대상 영역</div>
<template>
```

## drop
- 드래그를 놓을 대상에게 드래그를 놓았을때.
```vue
<script>
  ...
  methods:{
    func_drop(){
      console.log("드래그 놓음")
    }
  }
  ...
</script>

<template>
  <div @drop.prevent = "func_drop">드래그 놓을 대상 영역</div>
<template>
```

## 사용예시
- 다른 속성들도 존재하지만 기본적인 동작은 위의 네가지로 구현이 가능했다.
- 위치 변경을하는 모듈을 작업하면서 사용하였음.
- dragstart : 순서를 이동하려는 대상의 현재 순서를 저장하고 있는 번호와 배열의 인덱스를 저장함
- dragover : 이동 할 위치의 순서를 저장하고 있는 번호와 배열의 인덱스를 저장함 그리고 css로 하이라이트 처리
- dragleave : css하이라이트 처리 제거
- drop : 저장해둔 순서 값과 배열 인덱스로 순서변경 처리를 하고, css 하이라이트 처리 제거
