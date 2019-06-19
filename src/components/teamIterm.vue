<template>
  <div class="teamIterm">
    <div class="default-view">
      <img src="../assets/IMG_2683.jpg" alt class="pic">
      <div class="text-wrap">
        <h3>曾 蓓</h3>
        <span class="job-title">首席科学顾问</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "teamIterm"
};
</script>

<style lang="scss" scoped>
@import "../style/global.scss";

.teamIterm {
    position: relative;
        
  &:after {
    content: "";
    z-index: -1;
    position: absolute;
    top: -40px;
    left: -40px;
    display: block;
    width: 610px;
    height: 240px;
    background-color: white;
    box-shadow: 0px 16px 40px rgba(50, 50, 93, 0.14);
    border-radius: 8px;
  }
  .default-view {
    @include flex-all-center;

    img {
      width: 160px;
      height: 160px;
      border-radius: 80px;
      overflow: hidden;
      filter: contrast(0.9) saturate(0);
    }

    .text-wrap {
      margin-left: 40px;
      @include flex-column {
        align-items: flex-start;
      }

      h3 {
        @include font(32px, $font-color-black-1, 600);
        margin-bottom: 24px;
      }

      span {
        @include font(24px, $font-color-black-2, 400);
      }
    }
  }
}
</style>
