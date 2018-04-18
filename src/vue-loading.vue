<template>
  <div>
    <div class="loading-box" v-bind:class="this.directionStyle">
      <div class="container-box shadow">
        <div class="message">
          <p>Loading...</p>
        </div>
        <div class="image">
          <img src="https://loading.io/spinners/coolors/lg.palette-rotating-ring-loader.gif" alt="">
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
      background: String
    },
    data: {
      directionStyle: {
        'bottom-right': true,
        'bottom-left': false,
        'top-right': false,
        'top-left': false
      }
    },
    computed: {
      backgroundStyle () {
        return `background: ${this.direction}`
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
  width: 200px;
  height: 50px;
  margin: 50px;

  color: #777;
  font-size: 30px;

  display: flex;
  justify-content: center;
  align-items: center;
}
.container-box .message p {
  font-family: 'Nunito', sans-serif;
  max-width: 50%;
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
