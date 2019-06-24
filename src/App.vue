<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style lang="scss">
@import "../src/style/global.scss";
@import "../src/style/reset.css";
@import "../src/style/mobile.scss";

#app {
  width: 100vw;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  overflow-x: hidden;
}
body {
  overflow-x: hidden;
}
</style>
