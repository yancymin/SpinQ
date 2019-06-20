<template>
  <div class="news-card" :style="'background-image:' + 'url('+newsCard.bgImg+ ')'">
    <h4>{{newsCard.newsTitle}}</h4>
    <span class="date">{{newsCard.date}}</span>
  </div>
</template>

<script>
export default {
  name: "newsCard",
  props: ["newsCard"]
};
</script>

<style lang="scss" scoped>
@import "../style/global.scss";

.news-card {
  position: relative;
  width: 240px;
  height: 300px;
  background-color: white;
  padding: 24px;
  margin: 20px;
  background-size: cover;
  background-position: center;
  overflow: hidden;
  border-radius: 6px;
  text-align: left;
  @include flex-column {
    align-items: flex-start;
    justify-content: flex-end;
  }

  &::after {
    content: "";
    z-index: 0;
    position: absolute;
    bottom: 0;
    left: 0;
    display: block;
    width: 100%;
    height: 40%;
    background: linear-gradient(
      0,
      rgb(0, 0, 0) 0%,
      rgba(246, 249, 252, 0) 100%
    );
  }

  h4 {
    z-index: 99;
    margin-bottom: 8px;
    @include font(20px, white, 500) {
      line-height: 26px;
    }
  }

  .date {
    z-index: 99;
    @include font(12px, white, 400) {
      line-height: 17px;
    }
  }
}
</style>
