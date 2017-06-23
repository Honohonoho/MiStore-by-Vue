<template>
  <div id="app">
    <topBar></topBar>
  </div>
</template>

<script>
import 'normalize.css/normalize.css'
import './assets/reset.css'
import TopBar from './components/TopBar'

export default {
  components: {
    'topBar': TopBar
  }
}
</script>

<style>
#app {
  font-family: "Helvetica Neue", Helvetica, Arial, "Microsoft Yahei", "Hiragino Sans GB", "Heiti SC";
}
</style>
