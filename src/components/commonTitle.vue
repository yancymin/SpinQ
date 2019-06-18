
<template>
  <div class="common-title" :class="{left:titles.isRight}">
    <div>
      <img :src="titles.titleImg" alt class="mb-24">
      <div class="title_wrap">
        <span class="subTitle">{{titles.subTitle}}</span>
        <h1 class="title mb-48">{{titles.title}}</h1>
      </div>
    </div>
    <p class="des">{{titles.des}}</p>
  </div>
</template>

<script>
export default {
  name: "commonTitle",
  props: ["titleImg", "title", "subTitle", "des", "titles", "isRight"]
};
</script>

<style lang="scss" scoped>
@import "../style/global.scss";

.left {
  text-align: left;
  div {
    &:first-child {
      justify-content: flex-start;
      flex-direction: row !important;
      margin-bottom: 20px;

      .title_wrap {
        height: 104px;
        margin-left: 32px;
      }
    }
  }
}

.common-title {
  max-width: 440px;

  div {
    &:first-child {
      @include flex-column;
    }
  }

  @include flex-column;

  h1 {
    @include font(36px, $font-color-black-1, 400) {
      line-height: 50px;
    }
  }

  span {
    text-transform: uppercase;
    @include font(24px, $font-color-black-3, 700) {
      line-height: 30px;
    }
  }

  .des {
    @include font(18px, $font-color-black-2, 400) {
      line-height: 28px;
    }
  }
}
</style>


