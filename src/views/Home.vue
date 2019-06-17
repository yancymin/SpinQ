<template>
  <div class="home">
    <div class="header">
      <div class="header_wrap">
        <headerNav/>
      </div>
    </div>
  </div>
</template>

<script>
import headerNav from "../components/headerNav.vue";

export default {
  name: "home",
  components: {
    headerNav
  }
};
</script>

<style lang="scss" scoped>
.home {
  width: 100%;
  .header {
    display: flex;
    justify-content: center;
    width: 100vw;
    height: 80vh;
    background: linear-gradient(180deg, #0249ff 0%, #18d3fe 100%) no-repeat;
    &_wrap {
      max-width: 1280px;
      width: 90%;
    }
  }
}
</style>

