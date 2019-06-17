<template>
  <div class="headerNav">
    <div class="left">
      <img class="logo" src="../assets/nav_logo.svg" alt>
      <ul>
        <li><a href="">硬件</a></li>
        <li><a href="">软件</a></li>
        <li><a href="">团队介绍</a></li>
        <li><a href="">媒体报道</a></li>
        <li><a href="">人员招聘</a></li>
      </ul>
    </div>
    <div class="right">
      <ul class="lang">
        <li></li>
        <li></li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "headerNav",
  props: {}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../style/global.scss";

.headerNav {
  position: relative;
  // max-width: 1280px;
  // width: 100%;
  padding: 24px 0;
  border-bottom: 1px solid rgba(255, 255, 255, 0.18);
  @include flex-all-center {
    justify-content: space-between;
  }
  .left {
     @include flex-all-center;

     .logo {
       position: absolute;
       left: 0;
     }

     ul {
       margin-left: 200px;
        @include flex-all-center;

        li {
          @include font(14px,white,400);
          margin-right: 40px;
        }
     }
  }

}
</style>
