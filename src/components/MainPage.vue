<template>
  <div class="main">
    <div class="main-top">
      <mainNav></mainNav>
      <mainCarousel></mainCarousel>
      <mainRecommend></mainRecommend>
    </div>
    <div class="main-page">
      <!--小米明星单品-->
      <starGoods></starGoods>
      <!--家电-->
      <householdAppliances></householdAppliances>
      <!--智能-->
      <intelligence></intelligence>
      <!--搭配-->
      <collocation></collocation>
      <!--配件-->
      <parts></parts>
      <!--周边-->
      <relatedProducts></relatedProducts>
      <!--为你推荐-->
      <recommend></recommend>
      <!--热评产品-->
      <hotGoods></hotGoods>
      <!--内容-->
      <miContent></miContent>
      <!--视频-->
      <miVideo></miVideo>
    </div>
  </div>
</template>

<script>
import MainNav from './MainNav'
import MainCarousel from './MainCarousel'
import MainRecommend from './MainRecommend'
import StarGoods from './StarGoods'
import HouseholdAppliances from './HouseholdAppliances'
import Intelligence from './Intelligence'
import Collocation from './Collocation'
import Parts from './Parts'
import RelatedProducts from './RelatedProducts'
import Recommend from './Recommend'
import HotGoods from './HotGoods'
import MiContent from './MiContent'
import MiVideo from './MiVideo'

export default {
  components: {
    'mainNav': MainNav,
    'mainCarousel': MainCarousel,
    'mainRecommend': MainRecommend,
    'starGoods': StarGoods,
    'householdAppliances': HouseholdAppliances,
    'intelligence': Intelligence,
    'collocation': Collocation,
    'parts': Parts,
    'relatedProducts': RelatedProducts,
    'recommend': Recommend,
    'hotGoods': HotGoods,
    'miContent': MiContent,
    'miVideo': MiVideo
  }
}
</script>

<style lang="scss">
.main{
  >.main-top{
    width: 1226px;
    margin: 0 auto;
    background: #fff;
    position: relative;
  }
  .main-page{
    background: #f5f5f5;
    margin: 0 auto;
  }
}
</style>


