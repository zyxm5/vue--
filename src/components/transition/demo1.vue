<template>
  <p>
      盒子的多个属性一起动画: width, height, background-color, transform.
      将光标悬停在盒子上查看动画。
    </p>
    <div class="box"></div>
</template>
<style scoped>
.box {
  border-style: solid;
  border-width: 1px;
  display: block;
  width: 100px;
  height: 100px;
  background-color: #0000ff;
  -webkit-transition: width 2s, height 2s, background-color 2s,
    -webkit-transform 2s;
  transition: width 2s, height 2s, background-color 2s, transform 2s;
}
.box:hover {
  background-color: #ffcccc;
  width: 200px;
  height: 200px;
  -webkit-transform: rotate(180deg);
  transform: rotate(180deg);
}
</style>