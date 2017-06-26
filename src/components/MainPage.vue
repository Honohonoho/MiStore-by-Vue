<template>
  <div class="main-page">
    <div class="main-top">
      <mainNav></mainNav>
      <mainCarousel></mainCarousel>
      <mainRecommend></mainRecommend>
    </div>
    
  </div>
</template>

<script>
import MainNav from './MainNav'
import MainCarousel from './MainCarousel'
import MainRecommend from './MainRecommend'

export default {
  components: {
    'mainNav': MainNav,
    'mainCarousel': MainCarousel,
    'mainRecommend': MainRecommend
  }
}
</script>

<style lang="scss">
.main-page{
  width: 1226px;
  margin: 0 auto;
  >.main-top{
    width: 1226px;
    position: relative;
  }
}
</style>


