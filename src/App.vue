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
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
