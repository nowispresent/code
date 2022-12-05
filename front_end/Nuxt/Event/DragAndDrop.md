# Drag and Drop
- Vue에서 드래그앤 드롭 구현에 사용하는 함수

## draggable = true
- 드래그 대상으로 지정하기
```vue.js
<div :draggable = "true" >드래그 할 대상 영역</div>
```

## dragstart
- 드래그 시작 이벤트, 드래그 대상으로 지정된 엘리먼트를 press down 하면 동작함
```vue.js
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
