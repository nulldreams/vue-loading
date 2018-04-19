<template>
<div>
  <div class="loading-box" :class="classObject">
    <!-- <div class="loading-box top"> -->
    <div class="container-box shadow">
      <div class="message">
        <p :style="textStyle">{{text}}</p>
      </div>
      <div class="image">
        <img :src="image" alt="">
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'vue-loader',
  props: {
    direction: String,
    image: String,
    background: String,
    text: String,
    textColor: String
  },
  data() {
    return {
      directionStyle: {
        'bottom-right': false,
        'bottom-left': false,
        'top-right': false,
        'top-left': false,
        'middle-right': false,
        'middle-left': false,
        'middle': false,
        'bottom': false,
        'top': false
      }
    }
  },
  watch: {
    direction: function(newVal, oldVal) {
      this.directionStyle[oldVal] = false
      this.directionStyle[newVal] = true
    }
  },
  mounted() {
    this.directionStyle[this.direction] = true
  },
  computed: {
    textStyle() {
      return `color: ${this.textColor} !important;`
    },
    classObject: function(direcion) {
      return this.directionStyle
    }
  }
}
</script>

<style lang="scss">
@import './assets/css/base/alignment';
@import './assets/css/base/colors';
.loading-box {
    position: fixed;
    font-family: 'Nunito', sans-serif;
    max-width: 100%;
    padding: 50px;
    box-sizing: border-box;
}

.container-box {
    background: #fff;
    width: 400px;
    max-width: 100%;
    border-radius: 0.50em;
    display: flex;
    align-items: center;
    overflow: hidden;
    padding: 20px;
}

.container-box .message {
    color: #777;
    font-size: 30px;
    text-align: left;
    flex-grow: 1;
}

.container-box .message p {
    max-width: 100%;
    font-size: 1.5rem;
}

.container-box .image {
    img {
        width: 80px;
    }
}

@media (max-width: 480px) {
  .loading-box {
    padding: 10px;
  }

  .container-box .message p {
      font-size: 1rem;
  }

  .container-box .image {
      img {
          width: 50px;
      }
  }
}
</style>
