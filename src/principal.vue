<template>
  <div>
    <div class="title">
      <h1>vue-loading</h1>
    </div>
    <div class="inputs">
      <div class="input">
        <input v-model="texto" type="text" name="" id="">
        <div class="icone"><p>text</p></div>
      </div>
      <div class="input">
        <input v-model="gif" type="text" name="" id="">
        <div class="icone"><p>GIF</p></div>
      </div>
    </div>
    <div class="buttons">
      <div class="item blue" @click="direcao = 'top-left'"><p>top-left</p></div>
      <div class="item red" @click="direcao = 'top-right'"><p>top-right</p></div>
      <div class="item pink" @click="direcao = 'middle-left'"><p>middle-left</p></div>
      <div class="item orange" @click="direcao = 'middle-right'"><p>middle-right</p></div>
      <div class="item yellow" @click="direcao = 'bottom-left'"><p>bottom-left</p></div>
      <div class="item red-soft" @click="direcao = 'bottom-right'"><p>bottom-right</p></div>
      <!-- <div class="item blue-light" @click="direcao = 'middle'"><p>middle</p></div> -->
      <!-- <div class="item orange-soft" @click="direcao = 'top'"><p>top</p></div> -->
      <!-- <div class="item black" @click="direcao = 'bottom'"><p>bottom</p></div> -->
    </div>
    <!-- <div class="codigo">
      <pre><code>&lt;vue-loader :direction=&quot;direcao&quot; :image=&quot;gif&quot; :text=&quot;texto&quot; text-color=&quot;#786fa6&quot;/&gt;</code></pre>
    </div> -->
    <vue-loader :direction="direcao" :image="gif" :text="texto" text-color="#786fa6"/>
  </div>
</template>
<script>
import vueLoader from './vue-loading'

export default {
  components: {
    vueLoader
  },
  data () {
    return {
      direcao: 'top-right',
      texto: 'Loading...',
      gif: 'https://loading.io/spinners/coolors/lg.palette-rotating-ring-loader.gif'
    }
  },
  methods: {
    direcaoChange (direction) {
      // this.direcao = direction
      this.direcao = 'top-right'
    }
  }
}
</script>

<style>
.codigo {
  display: flex;
  justify-content: center;
  align-content: center;
}
.codigo pre {
  background: #a59adb;
  padding: 20px;
  border-radius: .25em;
}

.inputs {
  /* background: tomato; */
  height: 80px;
  width: 30%;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin: 0 auto;
}

.inputs > .input {
  width: 80%;
  height: 80px;
  margin: 10px;
  display: flex;
  flex-direction: row;
}

.icone {
  height: 30px;
  background: rgb(202, 202, 202);
  border-top-right-radius: .25em;
  border-bottom-right-radius: .25em;
  font-family: 'GothamRnd-Book', sans-serif;
  padding: 10px;
}

.icone p {
  margin: 0 auto;
  line-height: 10px;

  color: #555;
}

.input > input {
  color: #888!important;
  background: #ececec;
  border: none;
  border-top-left-radius: .25em;
  border-bottom-left-radius: .25em;
  width: 100%;
  height: 30px;
  outline: none;
  padding: 10px;
  /* padding: 20px; */
}

body {
  background: #786fa6;
}
.title {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-top: 10%;
}
.title h1 {
  font-family: 'GothamRnd-Medium', sans-serif;
  color: #fff;

  font-size: 50px;
}
.buttons {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;

  width: 25%;
  margin: 0 auto;
  margin-top: 50px;
}
.buttons > .item {
  width: 120px;
  height: 50px;

  margin: 10px;

  background: #778beb;

  /* line-height: 40px; */

  border-radius: .35em;
}

.item p {
  color: #fff;
  font-family: 'GothamRnd-Medium', sans-serif;

  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 15px;
}
</style>
