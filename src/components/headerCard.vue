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
  position: relative;
  max-width: 320px;
  width: 100%;
  padding: 18px 24px 24px 24px;
  box-shadow: 0px 2px 3px rgba(0, 0, 0, 0.14);
  border-radius: 8px;
  background-color: white;
  cursor: pointer;
  transition: all 0.3s ease;

&:hover {
  box-shadow: 0px 6px 20px rgba(0, 0, 0, 0.06);
  transform: translateY(-6px);

  &::before {
    transform: translateX(8px);
  }
  }

  &::before {
    content: "";
    position: absolute;
    right: 30px;
    top: 24px;
    display: block;
    width: 28px;
    height: 28px;
    background-image: url("../assets/card_arrow.svg");
    background-size: 28px 28px;
  transition: all 0.2s ease-out;

  }
  @include flex-column {
    align-items: flex-start;
  }

  h2 {
    @include font(28px, $font-color-black-1, 400);
  }

  span {
     text-transform: uppercase;
    margin-bottom: 10px;
    @include font(18px, $font-color-black-3, 600);
  }

  .icon {
    margin-bottom: 24px;
  }
}
</style>

