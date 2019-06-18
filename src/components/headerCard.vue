<template>
  <div class="headerCard">
    <img :src="headerCard.iconSrc" alt class="icon">
    <span class="sub-title">{{headerCard.subTitle}}</span>
    <h2>{{headerCard.title}}</h2>
  </div>
</template>

<script>
export default {
  name: "headerCard",
  props: ["title", "subTitle", "iconSrc", "headerCard"]
};
</script>

<style lang="scss" scoped>
@import "../style/global.scss";

.headerCard {
    max-width: 320px;
  width: 100%;
  padding: 18px 24px 24px 24px;
  box-shadow: 0px 2px 3px rgba(0, 0, 0, 0.14);
  border-radius: 8px;
  background-color: white;
  @include flex-column {
    align-items: flex-start;
  }

  h2 {
    @include font(28px, $font-color-black-1, 400);
  }

  span {
    margin-bottom: 10px;
    @include font(18px, $font-color-black-3, 400);
  }

  .icon {
    margin-bottom: 24px;
  }
}
</style>

