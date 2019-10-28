<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link>|
      <router-link to="/about">About</router-link>|
      <router-link to="/classification">分类</router-link>
    </div>
    <router-view class="view" />
  </div>
</template>

<style lang="less">
@import "./css/_variable.less";

#app {
  //布局
  display: flex;
  flex-direction: column-reverse;

  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;  //抗锯齿
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: @color-bottom;
  box-sizing: border-box; //border不占空间
  margin: 0;              //默认0
  padding: 0;

  height: 100vh;

  .view{
    flex-grow: 1;
  }
}
</style>
