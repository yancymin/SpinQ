<template>
  <div class="global-footer">
    <div class="footer-container">
      <div class="top bo-b">
        <img src="../assets/nav_logo.svg" alt class="logo">
        <div class="social">
          <div class="wechat"></div>
          <a class="zhihu" target="_blank" href="https://www.zhihu.com/org/shen-zhen-liang-xuan-ke-ji-you-xian-gong-si/activities">| SpinQ 专栏</a>
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
  name: 'globalFooter',
};
</script>

<style lang="scss" scoped>
@import "../style/global.scss";

.global-footer {
  width: 100vw;
  padding: 45px 0 18px 0;
  background: #32325d;
  @include flex-all-center;

  .footer-container {
    width: 100%;
    max-width: 1280px;
    margin:0  24px;
    @include flex-all-center;
  }

  .top {
    border-color: rgba(255, 255, 255, 0.2);
    width: 100%;
    padding-bottom: 45px;
    @include flex-all-center {
      justify-content: space-between;
    }

    .social {
      @include flex-all-center;
      .wechat {
          position: relative;
        cursor: pointer;
        width: 32px;
        height: 32px;
        background-image: url("../assets/wechat.svg");
        background-repeat: no-repeat;
        background-position: center;
        background-color: rgba(255, 255, 255, 0.15);
        border-radius: 32px;
        margin-right: 16px;
        transition: all 0.2s ease;

        &:hover {
          background-color: rgba(255, 255, 255, 0.2);

          &::before {
              opacity: 1;
          }
        }

        &::before {
            content: "";
            opacity: 0;
            position: absolute;
            top: -96px;
            left: -26px;
            display: block;
            width: 80px;
            height: 80px;
            border-radius: 4px;
            padding: 4px;
            background: url("../assets/QR.jpg") no-repeat center;
            background-size: cover;
            background-color: white;
                box-shadow: 0px 2px 10px rgba(50, 50, 93, 0.25);
                transition: all 0.25s ease;
        }

      }

      .zhihu {
        cursor: pointer;
        width: 112px;
        height: 32px;
        background-image: url("../assets/zhihu.svg");
        background-repeat: no-repeat;
        background-position: 12px center;
        background-color: rgba(255, 255, 255, 0.15);
        border-radius: 32px;
        padding-left: 17px;
        transition: all 0.2s ease;
        @include flex-all-center;
        @include font(14px, white, 400);

        &:hover {
          background-color: rgba(255, 255, 255, 0.2);
        }
      }
    }
  }

  .copyright {
    width: 100%;
    margin-top: 12px;

    span {
      @include font(13px, rgba(255, 255, 255, 0.4), 400);
    }
    @include flex-all-center {
      justify-content: space-between;
    }
  }
}
</style>
