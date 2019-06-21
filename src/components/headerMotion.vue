<template>
  <div class="hero">
    <div class="wrapper">
      <div class="container" id="header-motion-container">
        <div class="sphere">
          <div class="ring"></div>
          <div class="ring"></div>
          <div class="ring"></div>
          <div class="ring"></div>
          <div class="ring"></div>
          <div class="ring"></div>
          <div class="ring"></div>
          <div class="ring"></div>
          <div class="ring"></div>
          <div class="ring"></div>
        </div>
        <div class="sphere">
          <div class="ring"></div>
          <div class="ring"></div>
          <div class="ring"></div>
          <div class="ring"></div>
          <div class="ring"></div>
          <div class="ring"></div>
          <div class="ring"></div>
          <div class="ring"></div>
          <div class="ring"></div>
          <div class="ring"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'headerMotion',
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style lang="scss">
.hero {
//   margin-top: 40px;
}

.wrapper {
  perspective: 800px;
  display: flex;
  justify-content: center;
  filter: blur(1.5px);
}

.container {
  transform: rotate3d(40deg,40deg,90deg);
  transform-style: preserve-3d;
  position: relative;
  display: flex;
  height: 600px;
  width: 600px;
  margin: 10px 0;
}

.sphere,
.ring {
  position: absolute;
  height: 100%;
  width: 100%;
  transform-style: preserve-3d;
  will-change: transform;
}

.sphere {
  animation: rotateSphere 50s linear infinite;
  &:nth-of-type(1) {
    @for $i from 1 through 10 {
      .ring:nth-of-type(#{$i}) {
        transform: rotate3d(0,1,0,$i * 18deg);
      }
    }
  }
  &:nth-of-type(2) {
    @for $i from 1 through 10 {
      .ring:nth-of-type(#{$i}) {
        transform: rotate3d(1,0,0,$i * 18deg);
      }
    }
  }
}

$colors: #40e0d0, #4ae2d2, #53e3d5, #5de5d7, #66e6d9, #70e8dc, #79e9de, #83ebe0,
  #8cece3, #96eee5;

.ring {
  border: 1px solid;
  box-sizing: border-box;
  border-radius: 50%;
  opacity: 0;
  animation: fadeIn 3000ms ease infinite;
  box-shadow: 0 0 80px rgba(#fff, 0.2), inset 0 0 80px rgba(#fff, 0.2);
  @for $i from 1 through 10 {
    &:nth-of-type(#{$i}) {
      border-color: nth($colors, $i);
      animation-delay: $i * 200ms;
    }
  }
}

@keyframes rotateSphere {
  to {
    transform: rotateX(360deg) rotateY(360deg);
  }
}

@keyframes fadeIn {
  from,
  to {
    opacity: 0;
  }
  50% {
    opacity: 1;
  }
}
</style>
