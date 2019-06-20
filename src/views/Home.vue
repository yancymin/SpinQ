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
      <section class="team ptb-140">
        <div class="container-lg">
          <commonTitle :titles="titles[5]"/>
          <h2>科学顾问</h2>
          <div class="teamIterms">
            <teamIterm v-for="(item, index) in teams" :key="index" :teams="item"/>
          </div>
        </div>
      </section>
      <section class="news">
        <div class="container-lg">
          <commonTitle :titles="titles[6]"/>
          <div class="news_scroll-wrap" id="news_scroll-wrap">
            <span class="cover" id="cover"></span>
            <div class="lt" id="lt">
              <newsCard v-for="(item, index) in newsCards[0].left" :key="index" :newsCard="item"/>
              <newsCard
                v-for="(item, index) in newsCards[0].left"
                :key="index + '-label'"
                :newsCard="item"
              />
            </div>
            <div class="rt" id="rt">
              <newsCard v-for="(item, index) in newsCards[0].right" :key="index" :newsCard="item"/>
              <newsCard
                v-for="(item, index) in newsCards[0].right"
                :key="index + '-label'"
                :newsCard="item"
              />
            </div>
            <button class="more-news" @click="newsScroll()" id="more-news">更多报道</button>
          </div>
        </div>
      </section>
      <section class="hire ptb-140">
        <div class="container-lg">
          <commonTitle :titles="titles[7]" class="mb-80"/>
          <ul class="hire_list">
            <li>
              <div class="default bo-t bo-b" @click="hireShow()" id="listIterm">
                <h4>软件工程师</h4>
              </div>
              <div class="content" id="hire-content">
                <p class="content_title">岗位职责</p>1. 负责公司产品相关软件的设计、开发和测试；
                <br>2. 负责撰写需求分析说明书、详细设计、使用手册等相关技术文档；
                <br>3. 参与公司研发的自有算法的集成。
                <p class="content_title">岗位要求</p>1. 电子、自动化、软件工程、计算机相关专业本科及以上学历；
                <br>2. 具有1-2年C/C++软件开发经验，基本功扎实，熟悉STL；
                <br>3. 熟悉GUI开发，具有QT Creator开发经验的优先；
                <br>4. 具有很强的学习能力和探索精神；
                <br>5. 具有独立工作能力，优秀的团队合作精神以及良好的沟通能力。
                <p class="content_title">招聘人数</p>1人
              </div>
            </li>
          </ul>
        </div>
      </section>
      <section class="cooperation ptb-140">
        <div class="container-lg">
          <img src="../assets/cooperation.png" alt>
        </div>
      </section>
    </main>
    <globalFooter/>
  </div>
</template>

<script>
import headerNav from "../components/headerNav.vue";
import headerMotion from "../components/headerMotion.vue";
import headerCard from "../components/headerCard.vue";
import commonTitle from "../components/commonTitle.vue";
import teamIterm from "../components/teamIterm.vue";
import newsCard from "../components/newsCard.vue";
import globalFooter from "../components/globalFooter.vue";
import icon_1 from "../assets/icon_1.svg";
import icon_2 from "../assets/icon_2.svg";
import icon_3 from "../assets/icon_3.svg";
import icon_4 from "../assets/icon_4.svg";
import icon_5 from "../assets/icon_5.svg";
import icon_6 from "../assets/icon_6.svg";
import icon_7 from "../assets/icon_7.svg";
import icon_8 from "../assets/icon_8.svg";
import team_1 from "../assets/team_1.png";
import team_2 from "../assets/team_2.png";
import team_3 from "../assets/team_3.png";
import team_4 from "../assets/team_4.png";
import team_5 from "../assets/team_5.png";
import team_6 from "../assets/team_6.png";
import news_1 from "../assets/news_1.jpg";
import news_2 from "../assets/news_2.jpg";
import news_3 from "../assets/news_3.jpg";
import news_4 from "../assets/news_4.jpg";
import news_5 from "../assets/news_5.jpg";

export default {
  name: "home",
  components: {
    headerNav,
    headerMotion,
    headerCard,
    commonTitle,
    teamIterm,
    newsCard,
    globalFooter
  },
  methods: {
    newsScroll: function() {
      const more = document.getElementById("more-news");
      const cover = document.getElementById("cover");
      const lt = document.getElementById("lt");
      const rt = document.getElementById("rt");

      more.classList.add("hidden-1");
      cover.classList.add("hidden-2");
      lt.classList.add("newsScroll");
      rt.classList.add("newsScroll");
    },

    hireShow: function() {
      const listIterm = document.getElementById("listIterm");
      const hireContent = document.getElementById("hire-content");

      listIterm.classList.toggle("list-iterm-open");

      if (listIterm.className === "default bo-t bo-b list-iterm-open") {
        hireContent.classList.add("content-show");
      } else {
        hireContent.classList.remove("content-show");
      }
    }
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
        },
        {
          title: "媒体报道",
          subTitle: "SpinQ News",
          des: "",
          titleImg: icon_7,
          isRight: false
        },
        {
          title: "人才招聘",
          subTitle: "SpinQ Hire",
          des: "",
          titleImg: icon_8,
          isRight: false
        }
      ],
      teams: [
        {
          name: "曾 蓓",
          jobTitle: "首席科学顾问",
          des:
            "香港科技大学物理系教授，麻省理工学院物理学博士，清华大学首届基科班本科，从事量子计算研究近20年。",
          img: team_1
        },
        {
          name: "俞大鹏",
          jobTitle: "首席科学顾问",
          des: "中国科学院院士，北京大学物理学院教授，中国南方科技大学教授。",
          img: team_2
        },
        {
          name: "刘 松",
          jobTitle: "技术顾问",
          des:
            "量子器件与芯片加工中心主任，北京大学博士，长期从事量子器件的微纳加工研究。",
          img: team_3
        },
        {
          name: "鲁大为",
          jobTitle: "技术顾问",
          des:
            "南方科技大学物理系教授，中国科学技术大学物理学博士，长期从事量子计算研究。",
          img: team_4
        },
        {
          name: "苗国兴",
          jobTitle: "技术顾问",
          des:
            "滑铁卢大学电子系教授，布朗大学物理学博士，长期从事拓扑量子计算研究。",
          img: team_5
        },
        {
          name: "陈远珍",
          jobTitle: "技术顾问",
          des:
            "南方科技大学量子计算研究所副所长，美国马里兰大学博士，长期从事量子信息和量子材料方面的研究。",
          img: team_6
        }
      ],
      newsCards: [
        {
          left: [
            {
              newsTitle: "深圳市科创委领导一行了解小型仪器研发进展",
              date: "2019/05/09",
              bgImg: news_1
            },
            {
              newsTitle: "量旋科技于南科大开放日展示桌面型量子计算教学仪器",
              date: "2019/04/13",
              bgImg: news_2
            },
            {
              newsTitle: "量旋科技发布桌面型量子计算教学仪器",
              date: "2019/04/03",
              bgImg: news_3
            }
          ],
          right: [
            {
              newsTitle: "量旋科技发布首款开放控制层的核磁共振量子云平台",
              date: "2018/11/10",
              bgImg: news_4
            },
            {
              newsTitle:
                "深圳量旋科技（SpinQ）正式注册成立 致力量子计算商业化和普及化",
              date: "2018/08/27",
              bgImg: news_5
            }
          ]
        },
        {
          newsTitle: "深圳市科创委领导一行了解小型仪器研发进展",
          date: "2019/05/09",
          bgImg: news_1
        },
        {
          newsTitle: "量旋科技于南科大开放日展示桌面型量子计算教学仪器",
          date: "2019/04/13",
          bgImg: news_1
        },
        {
          newsTitle: "量旋科技发布桌面型量子计算教学仪器",
          date: "2019/04/03",
          bgImg: news_1
        },
        {
          newsTitle: "量旋科技发布首款开放控制层的核磁共振量子云平台",
          date: "2018/11/10",
          bgImg: news_1
        },
        {
          newsTitle:
            "深圳量旋科技（SpinQ）正式注册成立 致力量子计算商业化和普及化",
          date: "2018/08/27",
          bgImg: news_1
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
    background: linear-gradient(180deg, hsl(223, 80%, 30%) 0%, #18d3fe 100%)
      no-repeat;

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
            @include font(18px, $font-color-black-1, 500);

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

        .teamIterms {
          width: 100%;
          @include flex-all-center {
            flex-wrap: wrap;
          }
        }
      }
    }

    .news {
      overflow: hidden;
      .container-lg {
        position: relative;
        max-height: 740px;
        max-width: 1080px;
        padding: 0 40px 0 148px;
        background-color: $gray;
        border-radius: 8px;
        @include flex-all-center {
          justify-content: space-between;
        }

        .common-title {
          position: relative;
          left: 76px;
        }

        .news_scroll-wrap {
          position: relative;
          height: 100%;
          max-height: 740px;
          overflow-y: hidden;
          display: flex;
          justify-content: center;
          align-content: center;
          flex-wrap: wrap;

          .cover {
            z-index: 999;
            position: absolute;
            bottom: 0;
            left: 0;
            display: block;
            width: 100%;
            height: 260px;
            background: linear-gradient(
              0,
              #f6f9fc 65%,
              rgba(255, 255, 255, 0) 90%
            );
            transition: all 0.3s ease;
          }

          .lt {
            position: relative;
            top: -100px;
            margin-right: -20px !important;
          }

          .newsScroll {
            animation-delay: 0.3s;
            animation: newsScroll 40s linear infinite forwards;
          }

          @keyframes newsScroll {
            0% {
              transform: translate3d(0, 0, 0);
            }

            to {
              transform: translate3d(0, 740px, 0);
            }
          }

          .hidden-1 {
            opacity: 0;
            visibility: hidden;
            transform: translateY(20px);
          }

          .hidden-2 {
            opacity: 0;
            transform: translateY(20px);
            transition-delay: 0.15s;
          }

          button {
            z-index: 1000;
            position: absolute;
            bottom: 60px;
            left: 40%;
            width: 180px;
            height: 45px;
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
          }
        }
      }
    }

    .hire {
      width: 100%;
      padding-bottom: 0 !important;
      .container-lg {
        @include flex-column;

        .hire_list {
          width: 100%;
          @include flex-column {
            align-items: center;
          }
          li {
            position: relative;
            width: 80%;
            text-align: left;

            .default {
              z-index: 99;
              position: relative;
              padding: 24px 16px;
              cursor: pointer;
              transition: all 0.3s ease;
              @include flex-all-center {
                justify-content: flex-start;
              }
              @include font(24px, $font-color-black-1, 400);

              &:hover {
                background-color: $gray;
              }

              h4 {
                padding: 8px 0px;
              }

              &:before {
                content: "";
                display: block;
                width: 40px;
                height: 40px;
                background-image: url("../assets/hire_1.svg");
                background-size: cover;
                margin-right: 20px;
              }
              &:after {
                content: "";
                position: absolute;
                right: 8px;
                top: 37px;
                display: block;
                width: 14px;
                height: 14px;
                background-image: url("../assets/hire_2.svg");
                background-size: cover;
                margin-right: 20px;
              }
            }

            .content {
              z-index: 0;
              cursor: default;
              opacity: 0;
              position: absolute;
              top: 60px;
              padding: 40px 40px 40px 60px;
              transition: all 0.2s ease;
              // transform: scaleY(0.9);
              // transform-origin: top;
              @include font(16px, $font-color-black-2, 400) {
                line-height: 22px;
              }

              &_title {
                font-weight: 500px;
                font-size: 20px;
                color: $font-color-black-1;
                margin: 32px 0 16px 0;
              }
            }

            .list-iterm-open {
              padding-bottom: 510px;
              align-items: flex-start;
              transition: all 0.3s ease;
              box-shadow: 0px 2px 3px rgba(0, 0, 0, 0.14);
              border-color:transparent;
              border-radius: 8px;

              &:hover {
                background-color: transparent;
              }

              h4 
              {
              font-weight: 500;
              }
            }

            .content-show {
              opacity: 1;
              transition: all 0.3s ease;
              // transition-delay: 0.1s;
            }
          }
        }
      }
    }

    .cooperation {
      width: 100%;

      .container-lg {
        @include flex-all-center;
      }
      img {
        height: 150px;
      }
    }
  }
}
</style>

