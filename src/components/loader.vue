<template lang="html">
<div class="background-loader" :style="[loaderStyle]">
  <div class="rounded-ball" :style="[ballStyle]">
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
        borderColor: this.color + ' ' + this.color + ' ' + this.color + ' ' + 'transparent',
        borderWidth: this.borderWidth + 'px',
        borderStyle: 'solid',
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
    borderWidth: {
      type: Number,
      default: 10
    },
    duration: {
      type: Number,
      default: 10
    },
    size: {
      type: Number,
      default: 50
    }
  }
}
</script>

<style lang="scss">
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

@keyframes rotate {
    from {
        transform: rotate(360deg);
    }
    to {}
}

.rounded-ball {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    animation-name: rotate;
    animation-duration: 0.5s;
    animation-fill-mode: backwards;
    animation-timing-function: linear;
    animation-iteration-count: infinite;
}
</style>
