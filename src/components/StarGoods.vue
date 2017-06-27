<template>
  <div class="star-goods">
    <h2>小米明星单品</h2>
    <div class="goods-container">
      <div class="goods-item" v-for="(item,index) in starGoods" :key="index">
        <a :href="item.link">
          <img :src="item.imgUrl" alt="">
          <p class="title">{{item.title}}</p>
        </a>
        <p class="text">{{item.text}}</p>
        <p class="price">{{item.price}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return{
      starGoods: [
        {title: '小米5c 64GB 移动版', text: '直降200元，轻薄金属机身', price: '1299元', imgUrl: './static/img/stargoods-1.png', link: 'https://item.mi.com/product/10000030.html'},
        {title: '小米5s Plus', text: '64GB版本，下单立减200元', price: '2099元起', imgUrl: './static/img/stargoods-2.png', link: 'https://item.mi.com/product/10000025.html'},
        {title: '小米MIX', text: '下单立减200元，领券再减50元', price: '3249元起', imgUrl: './static/img/stargoods-3.png', link: 'https://item.mi.com/product/10000022.html'},
        {title: '小米电视4A 43英寸', text: '老人小孩都会用的人工智能语音电视', price: '2099元', imgUrl: './static/img/stargoods-4.png', link: 'https://item.mi.com/product/5348.html'},
        {title: '小米平板3', text: '今早10点开售', price: '1499元', imgUrl: './static/img/stargoods-5.png', link: 'https://www.mi.com/mipad3/'}
      ]
    }
  }
}
</script>

<style lang="scss">
.star-goods{
  width: 1226px;
  margin: 0 auto;
  margin-top: 26px; 
  h2{
    font-size: 22px;
    font-weight: 200;
    line-height: 58px;
    color: #333;
  }
  .goods-container{
    height: 340px;
    width: 1226px;
    display: flex;
    justify-content: space-between;
    .goods-item{
      width: 234px;
      height: 300px;
      background: #fafafa;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      transition: all .2s linear;
      &:hover{
        box-shadow: 0 15px 30px rgba(0,0,0,0.1);
        margin-top: -1px;
      }
      &:nth-child(1){
        border-top: 1px solid #ffac13;
      }
      &:nth-child(2){
        border-top: 1px solid #83c44e;
      }
      &:nth-child(3){
        border-top: 1px solid #2196f3;
      }
      &:nth-child(4){
        border-top: 1px solid #e53935;
      }
      &:nth-child(5){
        border-top: 1px solid #00c0a5;
      }
      a{
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        font-size: 14px;
        font-weight: 400;
        img{
          width: 160px;
          height: 160px;
        }
      }
      .text{
        color: #b0b0b0;
        font-size: 12px;
        margin-top: 10px;
        margin-bottom: 15px;
      }
      .price{
        color: #ff6709;
        font-size: 14px;
      }
    }
  }
}
</style>


