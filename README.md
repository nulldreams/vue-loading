<p align="center">
  <img src="./logo.png">
</p>
<h4 align="center">A Vue2 loader</h4>
<p align="center">
	
  <a href="https://github.com/nulldreams/vue-loading/issues">
      <img src="https://img.shields.io/codeclimate/issues/github/me-and/mdf.svg">
  </a>

  <a href="http://makeapullrequest.com">
      <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square">
  </a>
</p>
<p align="center">
  <a href="#install">Install</a> •
  <a href="#how-to-use">How To Use</a> •
</p>

## Install
`npm i @nulldreams/vue-loading`

## How to use
```html
<template>
  <div>
    <vue-loader direction="middle" image="https://loading.io/spinners/coolors/lg.palette-rotating-ring-loader.gif" text="Loading..." text-color="#786fa6" />
    <loader :color="'#cf6a87'" :borderWidth="5" :duration="1.5" :size="25" :background="'#f5cd79'" />
    <loader :color="'#f5cd79'" :borderWidth="10" :duration="1" :size="70" :background="'#778beb'" />
    <loader :color="'#778beb'" :borderWidth="20" :duration=".5" :size="100" :background="'#cf6a87'" />
    <loader-dots :color="'#f5cd79'" :background="'#ea8685'" :duration="1" :size="15" />
  </div>
</template>

<script>
import vueLoader from '@nulldreams/vue-loading/src/vue-loading'
import loader from '@nulldreams/vue-loading/src/components/loader'
import loaderDots from '@nulldreams/vue-loading/src/components/dots'

export default {
    components: {
        vueLoader,
        loader,
        loaderDots
    }
}
</script>
```
