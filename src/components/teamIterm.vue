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
  name: 'teamIterm',
  props: ['teams'],
};
</script>

<style lang="scss" scoped>
@import "../style/global.scss";

.teamIterm {
  position: relative;
  width: 270px;
  // max-width: calc(600px - 64px);
  padding: 32px 48px 32px 16px;
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
        transform: translateY(-45px) translateX(-18px) scale(0.8);
      }

      span {
        transform: translateY(-60px) translateX(-17px) scale(0.8);
      }

      .des {
        opacity: 1 !important;
        transform: translateY(0) !important;
      }
    }
  }

  .default-view {
    @include flex-all-center {
      justify-content: flex-start;
    }

    img {
      width: 120px;
      height: 120px;
      border-radius: 80px;
      overflow: hidden;
      filter: hue-rotate(0deg) saturate(0.14);
      transition: all 0.3s ease;
    }

    .text-wrap {
      position: relative;
      max-width: 290px;
      margin-left: 30px;
      @include flex-column {
        align-items: flex-start;
      }

      h3 {
        @include font(24px, $font-color-black-1, 600);
        transition: all 0.3s ease;
        margin-bottom: 20px;
      }

      span {
        transition: all 0.3s ease;
        @include font(18px, $font-color-black-2, 400);
      }

      .des {
        opacity: 0;
        position: absolute;
        text-align: left;
        left: -10px;
        width: 160px;
        top: 15px;
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
