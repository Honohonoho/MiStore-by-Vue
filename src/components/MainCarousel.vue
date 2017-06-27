<template>
  <div class="main-carousel">
    <div class="container">
      <transition-group name="fade" tag="div" class="fade">
        <div class="fade-item" v-for="(item,index) in fadeItems" v-show="index === curIndex" :key="index">
          <a :href="item.link">
            <img :src="item.imgUrl" alt="">
          </a>
        </div>
      </transition-group>
      <div class="play-pre" @click="playPre">
        <span class="icon"></span>
      </div>
      <div class="play-next" @click="playNext">
        <span class="icon"></span>
      </div>
      <div class="play-dot">
        <span class="dot" v-for="n in 5" :class="{active: n === curIndex + 1}" :key="n"></span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return{
      curIndex: 0,
      timeId: '',
      fadeItems: [
        {imgUrl: './static/img/xmad-1.jpg', link: 'https://item.mi.com/buyphone/redmi4x'},
        {imgUrl: './static/img/xmad-2.jpg', link: 'https://item.mi.com/product/10000030.html'},
        {imgUrl: './static/img/xmad-3.jpg', link: 'https://item.mi.com/product/10000029.html'},
        {imgUrl: './static/img/xmad-4.jpg', link: 'https://www.mi.com/buytv/'},
        {imgUrl: './static/img/xmad-5.jpg', link: 'https://www.mi.com/mibookair/'}
      ]
    }
  },
  mounted(){ //Vue2.0 替换了之前的ready，详见文档生命周期函数mounted
 		this.autoPlay()
  },
  methods: {
    playNext(){
      let lastIndex = this.fadeItems.length -1
      if(this.curIndex < lastIndex){
        this.curIndex += 1
      }else{
        this.curIndex = 0
      }
    },
    playPre(){
      let lastIndex = this.fadeItems.length - 1
      if(this.curIndex > 0){
        this.curIndex -= 1
      }else{
        this.curIndex = lastIndex
      }
    },
    autoPlay(){
      clearInterval(this.timeId)
      this.timeId = setInterval(()=>{
        this.playNext()
      }, 4000)
    }
  }
}
</script>

<style lang="scss">
  .main-carousel{
    position: absolute;
    left: 0;
    top: 0;
    width: 1226px;
    background: #fff;
    height: 460px;
    z-index: 1;
    .container{
      position: relative;
      height: 460px;
      .fade-item{
        position: absolute;
        left: 0;
        top: 0;
        width: 1226px;
        z-index: 1;
      }
      .play-pre{
        position: absolute;
        left: 234px;
        top: 50%;
        margin-top: -35px;
        z-index: 2;
        .icon{
          width: 41px;
          height: 69px;
          background: url(../assets/icon-slides.png) no-repeat;
          background-position: -83px 50%;
          display: inline-block;
          cursor: pointer;
          &:hover{
            background: url(../assets/icon-slides.png) no-repeat;
            background-position: 1px 50%;
          }
        }
      }
      .play-next{
        position: absolute;
        right: 0;
        top: 50%;
        margin-top: -35px;
        z-index: 2;
        .icon{
          width: 41px;
          height: 69px;
          background: url(../assets/icon-slides.png) no-repeat;
          background-position: -124px 50%;
          display: inline-block;
          cursor: pointer;
          &:hover{
            background: url(../assets/icon-slides.png) no-repeat;
            background-position: -42px 50%;
          }
        }
      }
      .play-dot{
        position: absolute;
        z-index: 1;
        width: 100px;
        right: 20px;
        bottom: 20px;
        display: flex;
        justify-content: space-between;
        .dot{
          width: 6px;
          height: 6px;
          border: 2px solid rgba(255,255,255,0.5);
          border-radius: 50%;
          background: rgba(0,0,0,0.5);
        }
        .active{
          border-color: rgba(0,0,0,0.5);
          background: rgba(255,255,255,0.5);
        }
      }
    }
  }
.fade-enter-active, .fade-leave-active {
  transition: opacity .5s ease;
}
.fade-enter, .fade-leave-to /* .fade-leave-active in <2.1.8 */ {
  opacity: 0;
}
</style>
 