<template>
  <div id="app">
    <topBar></topBar>
    <topHeader></topHeader>
    <mainPage></mainPage>
    <miFooter></miFooter>
  </div>
</template>

<script>
import 'normalize.css/normalize.css'
import './assets/reset.css'
import TopBar from './components/TopBar'
import TopHeader from './components/TopHeader'
import MainPage from './components/MainPage'
import MiFooter from './components/MiFooter'

export default {
  components: {
    'topBar': TopBar,
    'topHeader': TopHeader,
    'mainPage': MainPage,
    'miFooter': MiFooter
  }
}
</script>

<style>
#app {
  font-family: "Helvetica Neue", Helvetica, Arial, "Microsoft Yahei", "Hiragino Sans GB", "Heiti SC";
}
</style>
