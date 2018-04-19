<template>
  <div>
    <div class="title">
      <a href="https://github.com/nulldreams/vue-loading" target="_blank"><h1>vue-loading</h1></a>
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

<style lang="scss">
  @import './src/assets/css/main.scss';
</style>
