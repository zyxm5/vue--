<template>
  <p>随便点击某处来移动球</p>
<div id="foo" ref="foo"></div>
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
  setup() {
    const foo = ref();
    document.addEventListener('click', function(e){
      foo.value.style.left = (e.clientX-25)+'px';
      foo.value.style.top = (e.clientY-25)+'px';
    },false);
    return {
      foo
    }
  },
})
</script>

<style scoped>
p {
  padding-left: 60px;
}

#foo {
  border-radius: 50px;
  width: 50px;
  height: 50px;
  background: #c00;
  position: absolute;
  top: 0;
  left: 0;
  transition:  all 1s;
}
</style>