<template>
  <div class="mobile-menu" id="mobile-menu" :class="{blue: isBlue}" v-show="isShow">
    <div class="top">
      <img src="../assets/nav_logo2.svg" alt>
      <!-- <svg
        @click.stop="menuClose()"
        id="menu-close"
        xmlns="http://www.w3.org/2000/svg"
        width="24"
        height="24"
        viewBox="0 0 24 24"
      >
        <path
          fill="black"
          d="M19 6.41L17.59 5 12 10.59 6.41 5 5 6.41 10.59 12 5 17.59 6.41 19 12 13.41 17.59 19 19 17.59 13.41 12z"
        ></path>
        <path d="M0 0h24v24H0z" fill="none"></path>
      </svg>-->
    </div>
    <div class="menu-container">
      <ul>
        <li>
          <a class="anchor" href="#hardware-anchor" @click="anchor()">硬件</a>
        </li>
        <li>
          <a class="anchor" href="#software-anchor" @click="anchor()">软件</a>
        </li>
        <li>
          <a class="anchor" href="#team-anchor" @click="anchor()">团队介绍</a>
        </li>
        <li>
          <a class="anchor" href="#news-anchor" @click="anchor()">媒体报道</a>
        </li>
        <li>
          <a class="anchor" href="#hire-anchor" @click="anchor()">人员招聘</a>
        </li>
      </ul>
    </div>
    <div class="bottom">
      <ul class="lang">
        <li>
          <img src="../assets/cn.svg" alt>中文
        </li>
        <li>
          <img src="../assets/um.svg" alt>Coming soon
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "mobileMenu",
  props: ["isBlue", "isAnchor"],
  data() {
    return {
      // isClose: false

      // isAnchor: true
    };
  },
  methods: {
    anchor: function() {
      this.$emit('triggerMobile',false)
    },
  }
};
</script>

<style lang="scss" scoped>
@import "../style/global.scss";

.close {
  // transform: translateX(-100%) !important;
  opacity: 0 !important;
}

.blue {
  background-color: #0f3b90 !important;
  border-color: rgba(225, 225, 232, 0.28) !important;
  li {
    color: white !important;
  }
  .bottom {
    border-color: rgba(225, 225, 232, 0.28) !important;
  }
}

.mobile-menu {
  opacity: 0;
  display: none !important;
  position: relative;
  z-index: 9990;
  position: fixed;
  top: 58px;
  left: 0;
  // width: calc(100vw - 40px);
  // height: calc(100vh - (16px + 58px));
  width: calc(100vw - 40px);
  height: calc(100vh - 74px);
  background-color: white;
  padding: 0 20px 16px 20px;
  transition: all 0.2s ease-out;
  // transform: translateX(-100%);
  border-top: 1px solid #e1e1e8;

  @include flex-column {
    justify-content: space-between;
  }

  .top {
    border-bottom: 1px solid #e1e1e8;
    width: 100%;
    padding: 16px 0;
    display: none !important;

    img {
      height: 32px;
    }

    @include flex-all-center {
      justify-content: space-between;
    }
  }

  .menu-container {
    ul {
      padding: 24px 0;
      li {
        @include font(20px, $font-color-black-1, 400);
        margin: 48px 0;
      }
    }
  }

  .bottom {
    border-top: 1px solid #e1e1e8;
    padding-top: 18px;
    ul {
      @include flex-column {
        align-items: flex-start;
      }

      li {
        margin-bottom: 6px;
        padding: 7px 6px;
        @include flex-all-center {
          justify-content: flex-start;
        }
        @include font(14px, $font-color-black-1, 400);

        &:hover {
          background-color: $gray;
        }

        img {
          margin-right: 8px;
        }
      }
    }
  }
}
</style>
