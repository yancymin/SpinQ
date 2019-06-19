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
      <section class="software_1 ptb-140">
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
      <section class="software_2 ptb-80">
        <div class="container-lg">
          <div class="video"></div>
          <div class="right">
            <commonTitle :titles="titles[4]" class="pb-32 bo-b"/>
            <ul>
              <li>内置案例学习</li>
              <li>自定义量子线路</li>
              <li>量子知识点介绍</li>
              <li>量子游戏</li>
            </ul>
          </div>
        </div>
      </section>
      <section class="team ptb-140 bo-b">
        <div class="container-lg">
          <commonTitle :titles="titles[5]"/>
          <h2>科学顾问</h2>
          <div class="teamIterms">
            <teamIterm/>
          </div>
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
import teamIterm from "../components/teamIterm.vue";
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
    commonTitle,
    teamIterm
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
          titleImg: icon_4,
          isRight: true
        },
        {
          title: "桌面量子操控软件",
          subTitle: "SpinQ Software",
          des:
            "桌面端量子操控软件主要包括初级（内置案例学习）、进阶（自定义量子线路）、量子知识点介绍以及量子游戏和量子论坛模块。",
          titleImg: icon_5,
          isRight: true
        },
        {
          title: "我们的团队",
          subTitle: "SpinQ Team",
          des: "",
          titleImg: icon_6,
          isRight: false
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
    .software_1 {
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
            cursor: pointer;
            transition: all 0.3s ease;
            @include font(16px, white, 600);

            &:hover {
              opacity: 0.85;
              transform: translateY(-2px);
              box-shadow: 0px 6px 20px rgba(0, 0, 0, 0.2);
            }

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

    .software_2 {
      background-color: $gray;

      .right {
        max-width: 440px;
        ul {
          margin-top: 32px;
          @include flex-all-center {
            flex-wrap: wrap;
            justify-content: flex-start;
          }
          li {
            display: inline-block;
            background-color: white;
            padding: 12px 18px;
            border-radius: 50px;
            margin-right: 24px;
            margin-bottom: 24px;
            @include flex-all-center;
            @include font(18px, $font-color-black-1, 600);

            &:before {
              content: "";
              display: block;
              width: 32px;
              height: 32px;
              background-image: url("../assets/tag_icon.svg");
              background-size: 32px 32px;
              margin-right: 8px;
            }
          }
        }
      }
      .video {
        width: 750px;
        height: 550px;
        background-color: #0249ff;
        background-image: url("../assets/test.webp");
        background-size: 100% auto;
        border-radius: 8px;
        transform: rotate3d(-2.5, -0.866, 0, 24deg) rotateZ(-5deg);
        box-shadow: -27.1px 62.5px 125px -25px rgba(50, 50, 93, 0.5),
          -16.2px 37.5px 75px -37.5px rgba(0, 0, 0, 0.6);
      }
    }

    .team {
      .container-lg {
         @include flex-all-center {
           flex-direction: column;
         }

         h2 {
           margin: 60px 0;
            @include font(36px, $font-color-black-1, 400);

         }
      }
    }
  }
}
</style>

