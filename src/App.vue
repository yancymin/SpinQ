<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style lang="scss">
@import "../src/style/global.scss";
@import "../src/style/reset.css";

#app {
  width: 100vw;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body {
  overflow-x: hidden;
}
</style>
