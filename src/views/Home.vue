<template>
  <div class="home">
    <div class="header">
      <div class="text-wrap">
        <div class="text">
          <h1>
            致力于量子计算机的
            <strong>小型化</strong> 和
            <strong>商业化。</strong>
          </h1>
          <p>SpinQ 扎根于量子计算领域，专注于核磁共振桌面量子计算机的自主研发，推动量子计算的普及化和商业化。</p>
        </div>
        <headerMotion/>
      </div>
      <div class="header_wrap">
        <headerNav/>
      </div>

    </div>
      <div class="header_cards">
        <headerCard v-for="(item, index) in headerCards" :key="index" :headerCard="item"/>
      </div>
  </div>
</template>

<script>
import headerNav from "../components/headerNav.vue";
import headerMotion from "../components/headerMotion.vue";
import headerCard from "../components/headerCard.vue";
import icon_1 from "../assets/icon_1.svg";
import icon_2 from "../assets/icon_2.svg";
import icon_3 from "../assets/icon_3.svg";
import icon_4 from "../assets/icon_4.svg";
import icon_5 from "../assets/icon_5.svg";
import icon_6 from "../assets/icon_6.svg";
import icon_7 from "../assets/icon_7.svg";

export default {
  name: "home",
  components: {
    headerNav,
    headerMotion,
    headerCard
  },
  data() {
    return {
      headerCards: [
        { title: "桌面型量子计算机", subTitle: "SpinQ Hardware", iconSrc: icon_1 },
        { title: "软件介绍", subTitle: "SpinQ software", iconSrc: icon_4 },
        { title: "团队成员", subTitle: "SpinQ Team", iconSrc: icon_6 }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
@import "../style/global.scss";

.home {
  width: 100%;
  @include flex-all-center {
    flex-direction: column;
  }

  .header {
    display: flex;
    justify-content: center;
    width: 100vw;
    height: 780px;
    overflow: hidden;
    background: linear-gradient(180deg, #0249ff 0%, #18d3fe 100%) no-repeat;

    .text-wrap {
      width: 100%;
      z-index: 1000;
      position: absolute;
      text-align: center;
      margin: 120px 0;
      @include flex-all-center;

      .text {
        position: absolute;
        text-align: center;
        @include flex-all-center {
          flex-direction: column;
        }

        h1 {
          font-size: 64px;
          color: white;
          margin: 0 0 32px 0;
          font-weight: 300;
          margin-bottom: 32px;
        }

        p {
          color: white;
          font-size: 22px;
          max-width: 730px;
          width: 60%;
          line-height: 32px;
        }
        strong {
          font-weight: 600 !important;
        }
      }
    }

    &_wrap {
      max-width: 1280px;
      width: 90%;
      @include flex-column;
    }
  }

  .header_cards {
    z-index: 1000;
    position: relative;
    top: -90px;
    max-width: 1170px;
    width: 100%;
    @include flex-all-center {
      justify-content: space-between;
    }
  }
}
</style>

