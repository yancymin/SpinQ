<template>
  <div class="home">
    <div class="header">
      <div class="text-wrap">
        <div class="text">
          <h1>
            致力于量子计算机的
            <strong>小型化</strong> 和
            <strong>商业化</strong>
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
    <main>
      <section class="ptb-140 bo-b">
        <commonTitle :titles="titles[0]"/>
      </section>
      <section class="hardware_1 ptb-140 bo-b">
        <div class="container-lg">
          <img src="../assets/hardware_1.png" alt>
          <commonTitle :titles="titles[1]"/>
        </div>
      </section>
      <section class="hardware_2 ptb-140 bo-b">
        <div class="container-lg">
          <commonTitle :titles="titles[2]"/>
          <img src="../assets/hardware_2.png" alt>
        </div>
      </section>
      <section class="hardware_3 ptb-140 bo-b">
        <div class="container-lg">
          <div class="commonTitle_wrap">
            <commonTitle :titles="titles[3]" class="mb-48"/>
            <div class="buttons">
              <button>
                <i></i>技术论文
              </button>
              <button>云平台网址</button>
            </div>
          </div>
          <img src="../assets/software_1.png" alt>
        </div>
      </section>
    </main>
  </div>
</template>

<script>
import headerNav from "../components/headerNav.vue";
import headerMotion from "../components/headerMotion.vue";
import headerCard from "../components/headerCard.vue";
import commonTitle from "../components/commonTitle.vue";
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
    headerCard,
    commonTitle
  },
  data() {
    return {
      headerCards: [
        {
          title: "桌面型量子计算机",
          subTitle: "SpinQ Hardware",
          iconSrc: icon_1
        },
        { title: "软件介绍", subTitle: "SpinQ software", iconSrc: icon_4 },
        { title: "SpinQ 团队成员", subTitle: "SpinQ Team", iconSrc: icon_6 }
      ],
      titles: [
        {
          title: "桌面型量子计算机",
          subTitle: "SpinQ Hardware",
          des: "给量子计算科研入门者和爱好者带来不一样的体验",
          titleImg: icon_1,
          isRight: false
        },
        {
          title: "核磁共振",
          subTitle: "SpinQ Hardware",
          des:
            "在强磁场下，具有非零核自旋会处于不同的能量状态，利用相应的电磁波可以操控核自旋状态的跃迁和演化。",
          titleImg: icon_2,
          isRight: true
        },
        {
          title: "原型机",
          subTitle: "SpinQ Hardware",
          des:
            "桌面型核磁共振量子计算仪器体积小、稳定性好，具有量子计算的所有元素，并且操控简单，提供量子计算教学的整体解决方案。",
          titleImg: icon_3,
          isRight: true
        },
        {
          title: "量子计算云平台",
          subTitle: "SpinQ Software",
          des:
            "全球第一个开放底层脉冲控制的量子计算云平台，提供专业级的科研量子计算实验平台。",
          titleImg: icon_3,
          isRight: true
        }
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
        z-index: 999;
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

  main {
    width: 100vw;
    margin-top: -80px;
    @include flex-all-center {
      flex-direction: column;
    }

    section {
      width: 100%;
      @include flex-all-center;

      .container-lg {
        width: 100%;
        max-width: 1280px;
        @include flex-all-center {
          justify-content: space-between;
        }
      }
      &:nth-of-type(1) {
        width: 100%;
      }
    }

    .hardware_1 {
      img {
        height: 470px;
      }
    }
    .hardware_2 {
      img {
        height: 440px;
      }
    }
    .hardware_3 {
      img {
        height: 560px;
        margin-right: -160px;
      }

      .commonTitle_wrap {
        @include flex-column {
          align-items: flex-start;
        }

        .buttons {
          @include flex-all-center;

          button {
            width: 180px;
            height: 45px;
            //  padding: 12px 60px;
            margin-right: 12px;
            border: none;
            background-color: $blue;
            border-radius: 3px;
            @include font(16px, white, 400);

            &:nth-of-type(1) {
              @include flex-all-center;
              i {
                display: block;
                width: 40px;
                height: 40px;
                background-image: url("../assets/btn_icon_1.svg");
                background-size: 40px 40px;
                margin-left: -8px;
              }
            }
            &:nth-of-type(2) {
              background-color: $green;
            }
          }
        }
      }
    }
  }
}
</style>

