<template>
  <div class="headerNav">
    <div class="left">
      <img class="logo" src="../assets/nav_logo.svg" alt>
      <ul>
        <li>
          <a href="#hardware-anchor">硬件</a>
        </li>
        <li>
          <a href="#software-anchor">软件</a>
        </li>
        <li>
          <a href="#team-anchor">团队介绍</a>
        </li>
        <li>
          <a href="#news-anchor">媒体报道</a>
        </li>
        <li>
          <a href="#hire-anchor">人员招聘</a>
        </li>
      </ul>
    </div>
    <div class="right">
      <span>
        <svg
          width="18"
          height="18"
          viewBox="0 0 18 18"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M8.9925 1.5C4.8525 1.5 1.5 4.86 1.5 9C1.5 13.14 4.8525 16.5 8.9925 16.5C13.14 16.5 16.5 13.14 16.5 9C16.5 4.86 13.14 1.5 8.9925 1.5ZM14.19 6H11.9775C11.7375 5.0625 11.3925 4.1625 10.9425 3.33C12.3225 3.8025 13.47 4.7625 14.19 6ZM9 3.03C9.6225 3.93 10.11 4.9275 10.4325 6H7.5675C7.89 4.9275 8.3775 3.93 9 3.03ZM3.195 10.5C3.075 10.02 3 9.5175 3 9C3 8.4825 3.075 7.98 3.195 7.5H5.73C5.67 7.995 5.625 8.49 5.625 9C5.625 9.51 5.67 10.005 5.73 10.5H3.195ZM3.81 12H6.0225C6.2625 12.9375 6.6075 13.8375 7.0575 14.67C5.6775 14.1975 4.53 13.245 3.81 12ZM6.0225 6H3.81C4.53 4.755 5.6775 3.8025 7.0575 3.33C6.6075 4.1625 6.2625 5.0625 6.0225 6ZM9 14.97C8.3775 14.07 7.89 13.0725 7.5675 12H10.4325C10.11 13.0725 9.6225 14.07 9 14.97ZM10.755 10.5H7.245C7.1775 10.005 7.125 9.51 7.125 9C7.125 8.49 7.1775 7.9875 7.245 7.5H10.755C10.8225 7.9875 10.875 8.49 10.875 9C10.875 9.51 10.8225 10.005 10.755 10.5ZM10.9425 14.67C11.3925 13.8375 11.7375 12.9375 11.9775 12H14.19C13.47 13.2375 12.3225 14.1975 10.9425 14.67ZM12.27 10.5C12.33 10.005 12.375 9.51 12.375 9C12.375 8.49 12.33 7.995 12.27 7.5H14.805C14.925 7.98 15 8.4825 15 9C15 9.5175 14.925 10.02 14.805 10.5H12.27Z"
            fill="white"
          ></path>
        </svg>
        中文
      </span>
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
  name: 'headerNav',
  props: {},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../style/global.scss";

.headerNav {
  position: relative;
  padding: 24px 0;
  border-bottom: 1px solid rgba(255, 255, 255, 0.18);
  @include flex-all-center {
    justify-content: space-between;
  }
  .left {
    @include flex-all-center;

    .logo {
      position: absolute;
      left: 0;
    }

    ul {
      margin-left: 180px;
      @include flex-all-center;

      li {
        @include font(14px, white, 400);
        margin-right: 40px;

        a {
          position: relative;
          @include flex-all-center;
          &::before {
            z-index: 0;
            content: "";
            position: absolute;

            display: block;
            width: 100%;
            height: 100%;
            padding: 8px;
            border-radius: 4px;
            background-color: rgba(255, 255, 255, 0);
            transition: all 0.3s ease;
            transition-delay: 0.04s;
          }

          &:hover {
            &::before {
              background-color: rgba(255, 255, 255, 0.1);
            }
          }
        }
      }
    }
  }

  .right {
    border: 1px solid transparent;
    cursor: pointer;
    border-radius: 3px;
    transition: all 0.25s ease;

    &:hover {
      border: 1px solid rgba(255, 255, 255, 0.4);

      .lang {
        opacity: 1;
      }
    }

    @include flex-all-center;

    span {
      position: relative;
      padding: 8px;
      @include flex-all-center;
      @include font(14px, white, 400);

      svg {
        margin-right: 8px;
      }
    }
    .lang {
      opacity: 0;
      z-index: 10000;
      position: absolute;
      top: 70px;
      width: 148px;
      padding: 8px;
      background-color: white;
      text-align: left;
      border-radius: 4px;
      box-shadow: 0px 16px 40px rgba(50, 50, 93, 0.14);
      transition: all 0.2s ease-out;
      transition-delay: 0.18s;

      li {
        cursor: pointer;
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

@media screen and (max-width: 780px)  {
    .headerNav {
      .left {
          ul {
        display: none;
      }
      }
    }
}
</style>
