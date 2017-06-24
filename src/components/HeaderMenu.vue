<template>
  <div class="header-menu">
    <ul>
      <li v-for="item in miphone">
        <div class="product">
          <p class="info">{{item.info}}</p>
          <a href=""><img :src="item.imgUrl" alt=""></a>
          <p class="title">{{item.title}}</p>
          <p class="price">{{item.price}}</p>
        </div>
      </li>
    </ul>

  </div>
</template>

<script>
export default {
  data(){
    return{
      miphone: [
        {title: '小米6', imgUrl: './static/img/xm6.png', price: '2499元起', info: '新品'},
        {title: '小米Max 2', imgUrl: './static/img/max2.png', price: '1699元起', info: '新品'},
        {title: '小米Note 2', imgUrl: './static/img/xiaomiNOTE2.jpg', price: '2799元起', info: '现货'},
        {title: '小米MIX', imgUrl: './static/img/MIX.jpg', price: '3499元起', info: '现货'},
        {title: '小米5s Plus', imgUrl: './static/img/5splus.jpg', price: '2299元起', info: ''},
        {title: '小米手机5c', imgUrl: './static/img/mi5c.png', price: '1499元起', info: ''},
      ]
    }
  },
  methods: {
    // isInfo: function(){
    //   console.log(item)
    //   if(this.item.info.length != 0){
    //     this.isInfo = true
    //   }
    // }
  }
}
</script>

<style lang="scss">
.header-menu{
  position: absolute;
  bottom: 0;
  left: 0;
  width: 1226px;
  transform: translate(0,100%);
  height: 230px;
  border-top: 1px solid #e0e0e0;
  border-bottom: 1px solid #e0e0e0;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.15);
  >ul{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    display: flex;
    justify-content: flex-start;
    >li{
      width: 160px;
      .product{
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;
        a{
          border-right: 1px solid #e0e0e0;
        }
        a>img{
          width: 159px;
          height: 110px;
        }
        .info{
          line-height: 10px;
          height: 10px;
          padding: 5px 20px;
          margin-bottom: 20px;
          color: #ff6700;
          border: 1px solid #ff6700; 
        }
        .title{
          margin-top: 20px;
          margin-bottom: 5px;
          color: #333;
        }
        .price{
          color: #ff6700;
        }
      }
    }
  }
}
</style>
