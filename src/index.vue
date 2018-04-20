<template>
<div>

  <header>
    <div class="header">
      <div class="header__block">
        <div class="title">
          <a href="https://github.com/nulldreams/vue2-loading" target="_blank"><h1>vue2-loading</h1></a>
        </div>

        <div class="inputs">
          <div class="input">
            <input v-model="texto" type="text" name="" id="">
            <div class="icone">
              <p>text</p>
            </div>
          </div>
          <div class="input">
            <input v-model="gif" type="text" name="" id="">
            <div class="icone">
              <p>GIF</p>
            </div>
          </div>
        </div>

        <div class="buttons">
          <div class="item blue" @click="direcao = 'top-left'">
            <p>top-left</p>
          </div>
          <div class="item red" @click="direcao = 'top-right'">
            <p>top-right</p>
          </div>
          <div class="item pink" @click="direcao = 'middle-left'">
            <p>middle-left</p>
          </div>
          <div class="item orange" @click="direcao = 'middle-right'">
            <p>middle-right</p>
          </div>
          <div class="item yellow" @click="direcao = 'bottom-left'">
            <p>bottom-left</p>
          </div>
          <div class="item red-soft" @click="direcao = 'bottom-right'">
            <p>bottom-right</p>
          </div>
          <!-- <div class="item blue-light" @click="direcao = 'middle'"><p>middle</p></div> -->
          <!-- <div class="item orange-soft" @click="direcao = 'top'"><p>top</p></div> -->
          <!-- <div class="item black" @click="direcao = 'bottom'"><p>bottom</p></div> -->
        </div>
      </div>
      <!-- <div class="codigo">
          <pre><code class="html">&lt;vue-loader :direction=&quot;direcao&quot; :image=&quot;gif&quot; :text=&quot;texto&quot; text-color=&quot;#786fa6&quot;/&gt;</code></pre>
        </div> -->
      <vue-loader :direction="direcao" :image="gif" :text="texto" text-color="#786fa6" />
    </div>
  </header>


  <div class="container-examples">
    <div class="example full">
      <div class="example__loader">
        <loader :color="'#cf6a87'" :borderWidth="5" :duration="1.5" :size="25" :background="'#f5cd79'" />
      </div>
      <div class="example__code">
        <div class="code">
          <pre><code class="html">&lt;loader :color=&quot;'#cf6a87'&quot; :borderWidth=&quot;5&quot; :duration=&quot;1.5&quot; :size=&quot;25&quot; :background=&quot;'#f5cd79'&quot;/&gt;</code></pre>
        </div>
      </div>
    </div>

    <div class="example full">
      <div class="example__loader">
        <loader :color="'#f5cd79'" :borderWidth="10" :duration="1" :size="70" :background="'#778beb'" />
      </div>
      <div class="example__code">
        <pre><code class="html">&lt;loader :color=&quot;'#f5cd79'&quot; :borderWidth=&quot;10&quot; :duration=&quot;1&quot; :size=&quot;70&quot; :background=&quot;'#778beb'&quot;/&gt;</code></pre>
      </div>
    </div>

    <div class="example full">
      <div class="example__loader">
        <loader :color="'#778beb'" :borderWidth="20" :duration=".5" :size="100" :background="'#cf6a87'" />
      </div>
      <div class="example__code">
        <pre><code class="html">&lt;loader :color=&quot;'#778beb'&quot; :borderWidth=&quot;20&quot; :duration=&quot;.5&quot; :size=&quot;100&quot; :background=&quot;'#cf6a87'&quot; /&gt;</code></pre>
      </div>
    </div>

    <div class="example full">
      <div class="example__loader">
        <loader-dots :color="'#f5cd79'" :background="'#ea8685'" :duration="1" :size="15" />
      </div>
      <div class="example__code">
        <pre><code class="html">&lt;loader-dots :color=&quot;'#f5cd79'&quot; :background=&quot;'#ea8685'&quot; :duration=&quot;1&quot; :size=&quot;15&quot; /&gt;</code></pre>
      </div>
    </div>

  </div>


</div>
</template>
<script>
import vueLoader from './vue-loading'
import loader from '@/components/loader'
import loaderDots from '@/components/dots'

export default {
  components: {
    vueLoader,
    loader,
    loaderDots
  },
  data() {
    return {
      direcao: 'top-right',
      texto: 'Loading...',
      gif: 'https://loading.io/spinners/coolors/lg.palette-rotating-ring-loader.gif'
    }
  },
  methods: {
    direcaoChange(direction) {
      // this.direcao = direction
      this.direcao = 'top-right'
    }
  },
  created () {
    $(function () {
      hljs.configure({useBR: true})

      $('pre code').each(function(i, block) {
        hljs.highlightBlock(block)
      })
    })
  }
}
</script>

<style lang="scss">
@import './src/assets/css/main.scss';
</style>
<style>
@import './assets/css/dracula.css';
</style>