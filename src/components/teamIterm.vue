<template>
  <div class="teamIterm">
    <div class="default-view">
      <img :src="teams.img" alt class="pic">
      <div class="text-wrap">
        <h3>{{teams.name}}</h3>
        <span class="job-title">{{teams.jobTitle}}</span>
        <div class="des bo-t">
          <p>{{teams.des}}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "teamIterm",
  props: ["teams"]
};
</script>

<style lang="scss" scoped>
@import "../style/global.scss";

.teamIterm {
  position: relative;
  width: 344px;
  max-width: calc(600px - 64px);
  padding: 32px 40px 32px 32px;
  border-radius: 8px;
  transition: all 0.3s ease;
  margin-bottom: 24px;
  // box-shadow: 0px 16px 40px rgba(50, 50, 93, 0.14);

  &:hover {
    box-shadow: 0px 16px 40px rgba(50, 50, 93, 0.14);

    .default-view img {
      // transform: scale(1.05);
      filter: contrast(0.92);
    }

    .text-wrap {
      h3 {
        transform: translateY(-45px) translateX(-21px) scale(0.8);
      }

      span {
        transform: translateY(-60px) translateX(-22px) scale(0.8);
      }

      .des {
        opacity: 1 !important;
        transform: translateY(0) !important;
      }
    }
  }

  // &:after {
  //   content: "";
  //   z-index: -1;
  //   position: absolute;
  //   top: -40px;
  //   left: -40px;
  //   display: block;
  //   width: 610px;
  //   height: 240px;
  //   background-color: white;
  //   box-shadow: 0px 16px 40px rgba(50, 50, 93, 0.14);
  //   border-radius: 8px;
  // }
  .default-view {
    @include flex-all-center {
      justify-content: flex-start;
    }

    img {
      width: 160px;
      height: 160px;
      border-radius: 80px;
      overflow: hidden;
  filter: hue-rotate(9deg) saturate(0.2);
      transition: all 0.3s ease;
    }

    .text-wrap {
      position: relative;
      max-width: 290px;
      margin-left: 40px;
      @include flex-column {
        align-items: flex-start;
      }

      h3 {
        @include font(32px, $font-color-black-1, 500);
        transition: all 0.3s ease;
        margin-bottom: 20px;
      }

      span {
        transition: all 0.3s ease;
        @include font(24px, $font-color-black-2, 400);
      }

      .des {
        opacity: 0;
        position: absolute;
        text-align: left;
        left: -10px;
        width: 160px;
        top: 32px;
        padding-top: 12px;
        transform: translateY(-20px);
        transition: all 0.3s ease;

        @include font(13px, $font-color-black-2, 400) {
          line-height: 20px;
        }
      }
    }
  }
}
</style>
