<template>
  <div class="main-recommend">
    <div class="activities">
      <div class="item" v-for="(item,index) in activities" :key="index">
        <a :href="item.link">
          <img class="icon" :src="item.imgUrl" alt="">
          <span class="text">{{item.title}}</span>
        </a>
      </div>
    </div>
    <div class="rec-item" v-for="(item,index) in recommend" :key="index">
      <a :href="item.link"><img :src="item.imgUrl" alt=""></a>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      activities: [
        {title: '选购手机', imgUrl: './static/img/buyphone.png', link: 'https://www.mi.com/compare/'},
        {title: '企业团购', imgUrl: './static/img/gift.png', link: 'http://qiye.mi.com/'},
        {title: '一元活动', imgUrl: './static/img/one.png', link: 'https://1.hd.mi.com/'},
        {title: '小米移动', imgUrl: './static/img/sim.png', link: 'https://www.mi.com/mimobile/'},
        {title: '以旧换新', imgUrl: './static/img/renew.png', link: 'https://huanxin.mi.com/'},
        {title: '话费充值', imgUrl: './static/img/chongzhi.png', link: 'http://recharge.10046.mi.com/'}
      ],
      recommend: [
        {imgUrl: './static/img/xmad_1.jpg', link: 'https://item.mi.com/product/10000024.html'},
        {imgUrl: './static/img/xmad_2.jpg', link: 'https://item.mi.com/buyphone/redminote4x'},
        {imgUrl: './static/img/xmad_3.jpg', link: 'https://www.mi.com/dianfanbao2-4l/'}
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.main-recommend{
  width: 1226px;
  background: #fff;
  margin: 0 auto;
  height: 170px;
  margin-top: 14px;
  display: flex;
  justify-content: space-between;
  .activities{
    width: 234px;
    height: 170px;
    display: flex;
    flex-flow: wrap;
    align-content: center;
    background: #5f5750;
    .item{
      width: 70px;
      height: 70px;
      padding: 6px 3px;
      border: 1px solid #665e57;
      display: flex;
      align-items: center;
      justify-content: center;
      a{
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
        color: rgba(255,255,255,0.7);
        cursor: pointer;
        &:hover{
          color: rgba(255,255,255,1);
        }
        .icon{
          height: 32px;
          width: 32px;
          margin-bottom: 10px;
        }
      }
    }
  }
  .rec-item{
    width: 316px;
    height: 170px;
    transition: box-shadow .2s linear;
    a>img{
      width: 316px;
      height: 170px;
    }
    &:hover{
      box-shadow: 0 15px 30px rgba(0,0,0,0.1);
    }
  }
}
</style>

