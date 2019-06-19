<template>
  <div class="global-footer">
    <div class="footer-container">
      <div class="top bo-b">
        <img src="../assets/nav_logo.svg" alt class="logo">
        <div class="social">
          <div class="wechat"></div>
          <div class="zhihu"></div>
        </div>
      </div>
      <div class="copyright">
        <span>深圳量旋科技有限公司</span>
        <span>Copyright © 2019 SpinQ</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "globalFooter"
};
</script>

<style lang="scss" scoped>
@import "../style/global.scss";

.global-footer {
  width: 100vw;
  padding: 45px 0 18px 0;
  background: #0e58fe;
  @include flex-all-center;

  .footer-container {
    width: 100%;
    max-width: 1280px;
    @include flex-all-center;
  }

  .top {
      border-color: rgba(255,255,255,0.2);
      width: 100%;
    padding-bottom: 45px;
    @include flex-all-center {
      justify-content: space-between;
    }
  }

  .copyright {
      width: 100%;
      margin-top: 12px;

      span {
          @include font(13px,rgba(255,255,255,0.4),400)
      }
    @include flex-all-center {
      justify-content: space-between;
    }
  }
}
</style>


