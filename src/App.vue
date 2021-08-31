<template>
  <p>transition: <button v-for="(demo,index) in transitionDemos" :key="demo" @click="handleclick(demo)">{{ 'demo' + (index + 1) }}</button></p>
  <p>animation: <button v-for="(demo,index) in animationDemos" :key="demo" @click="handleClick(demo)">{{ 'demo' + (index + 1) }}</button></p>
  <component :is="component"/>
</template>
<script lang="ts">
import { defineComponent, reactive, ref } from '@vue/runtime-core';
import TransitionDemo1 from './components/transition/demo1.vue';
import TransitionDemo2 from './components/transition/demo2.vue';
import AnimationDemo1 from './components/animation/demo1.vue';
export default defineComponent({
  components: {
    TransitionDemo1,
    TransitionDemo2,
    AnimationDemo1
  },
  setup(){
    const component = ref('');
    const transitionDemos = reactive(['transition-demo1', 'transition-demo2']);
    const animationDemos = reactive(['animationDemo1', 'animationDemo2']);
    function handleClick(comp: string){
      component.value = comp;
    }
    return {
      component,
      transitionDemos,
      animationDemos,
      handleClick
    }
  }
})
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
