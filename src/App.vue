<template>
  <div id="app">
    <topBar></topBar>
    <topHeader></topHeader>
  </div>
</template>

<script>
import 'normalize.css/normalize.css'
import './assets/reset.css'
import TopBar from './components/TopBar'
import TopHeader from './components/TopHeader'

export default {
  components: {
    'topBar': TopBar,
    'topHeader': TopHeader
  }
}
</script>

<style>
#app {
  font-family: "Helvetica Neue", Helvetica, Arial, "Microsoft Yahei", "Hiragino Sans GB", "Heiti SC";
}
</style>
