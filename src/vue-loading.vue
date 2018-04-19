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
    data () {
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
      direction: function (newVal, oldVal) {
        this.directionStyle[oldVal] = false
        this.directionStyle[newVal] = true
      }
    },
    mounted () {
      this.directionStyle[this.direction] = true
    },
    computed: {
      textStyle () {
        return `color: ${this.textColor} !important;`
      },
      classObject: function (direcion) {
        return this.directionStyle
      }
    }
  }
</script>

<style>
@import './assets/style.css';
.loading-box {
  position: fixed;
}
.container-box {
  background: #fff;

  width: 500px;
  height: 150px;

  border-radius: .50em;

  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}
.container-box .message {
  /* max-width: 50%; */
  width: 300px;
  height: 50px;
  /* margin: 50px; */

  color: #777;
  font-size: 30px;

  display: flex;
  justify-content: center;
  align-items: center;
}
.container-box .message p {
  font-family: 'Nunito', sans-serif;
  max-width: 100%;
}
.container-box .image {
  width: 100px;
  height: 80px;
  margin: 50px;

  display: flex;
  justify-content: center;
  align-items: center;
}
.container-box .image img {
  width: 100%;
  height: auto;
}
</style>
