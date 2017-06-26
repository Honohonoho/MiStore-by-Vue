<template>
  <div class="main-recommend">
    <div class="activities">
      <div class="item" v-for="n in 6" :key="n">
        <a>
          <span class="icon"></span>
          <span class="text"></span>
        </a>
      </div>
    </div>
    <div class="rec-1">
      <a><img alt=""></a>
    </div>
    <div class="rec-2">
      <a><img alt=""></a>
    </div>
    <div class="rec-3">
      <a><img alt=""></a>
    </div>
  </div>
</template>

<script>
export default {
  // data(){
  //   retun {

  //   }
  // }
}
</script>

<style lang="scss" scoped>
.main-recommend{
  width: 1226px;
  height: 170px;
  margin-top: 14px;
}
</style>

