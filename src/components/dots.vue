<template lang="html">
<div class="background-loader" :style="[loaderStyle]">
  <div class="balls">
  <div class="ball ball1" :style="[ballStyle]"></div>
  <div class="ball ball2" :style="[ballStyle]"></div>
  <div class="ball ball3" :style="[ballStyle]"></div>
</div>
</div>
</template>

<script>
export default {
  data() {
    return {
      loaderStyle: {
        background: this.background,
      },
      ballStyle: {
        background: this.color,
        animationDuration: this.duration + 's',
        width: this.size + 'px',
        height: this.size + 'px'
      }
    }
  },
  props: {
    background: {
      type: String,
      default: 'rgba(0,0,0,.3)'
    },
    color: {
      type: String,
      default: 'red'
    },
    duration: {
      type: Number,
      default: 10
    },
    size: {
      type: Number,
      default: 50
    },
    distance: {
      type: Number,
      default: 50
    }
  }
}
</script>

<style lang="scss">
$distance: -60px;

.background-loader {
    min-height: 100%;
    width: 100%;
    position: absolute;
    top: 0;
    left: 0;
    z-index: 9999;
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
}

.balls {
    box-sizing: border-box;
    display: flex;
    justify-content: center;
    align-items: center;
}
.ball {
    width: 10px;
    height: 10px;
    background: #ddd;
    border-radius: 50%;
    margin: 5px;
    animation-name: jump;
    animation-fill-mode: forwards;
    animation-iteration-count: infinite;
}
@keyframes jump {
    0% {}
    50% {
        transform: translateY($distance);
    }
    100% {}
}
.ball1 {
    animation-delay: 0.1s;
}
.ball2 {
    animation-delay: 0.2s;
}
.ball3 {
    animation-delay: 0.3s;
}
</style>
