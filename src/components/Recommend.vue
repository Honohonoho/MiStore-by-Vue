<template>
  <div class="recommend">
    <h2>为你推荐</h2>
    <div class="container">
      <div class="wrapper">
        <div class="item" v-for="(item,index) in Items" :key="index"
            :class="{active: index === selected}"
            @mouseenter="selected = index" @mouseleave="selected = ''"
          >
          <a :href="item.link">
            <img :src="item.imgUrl">
          </a>
          <p class="title">{{item.title}}</p>
          <p class="price">{{item.price}}</p>
          <p class="text">{{item.text}}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return{
      selected: '',
      Items: [
        {title: '小米无人机4K版套装', text: '434人好评', price: '2999元', imgUrl: './static/img/rec-1.jpg', link: 'https://item.mi.com/1170300012.html'},
        {title: '小米电视3s 65英寸 影院版', text: '6456人好评', price: '6499元', imgUrl: './static/img/rec-2.jpg', link: 'https://item.mi.com/1163900098.html'},
        {title: 'Amazfit 运动手表', text: '5405人好评', price: '799元', imgUrl: './static/img/rec-3.jpg', link: 'https://item.mi.com/1164300010.html'},
        {title: '小米米家电动滑板车', text: '2059人好评', price: '1999元', imgUrl: './static/img/rec-4.jpg', link: 'https://item.mi.com/1164900005.html'},
        {title: '小米运动蓝牙耳机', text: '9431人好评', price: '149元', imgUrl: './static/img/rec-5.jpg', link: 'https://item.mi.com/1163900023.html'}
      ],
    }
  }
}
</script>

<style lang="scss" scoped>
.recommend{
  width: 1226px;
  margin: 0 auto;
  background: #f5f5f5;
  padding-top: 60px;
  h2{
    font-size: 22px;
    font-weight: 200;
    line-height: 58px;
    color: #333;
  }
  .container{
    width: 1226px;
    margin: 0 auto;
    .wrapper{
      display: flex;
      justify-content: space-between;
      align-content: space-between;
      .active{
        box-shadow: 0 15px 30px rgba(0,0,0,0.1);
        margin-top: -1px;
        transition: all .2s linear;
      }
      .item{
        position: relative;
        overflow: hidden;
        height: 300px;
        width: 234px;
        color: #333;
        background: #fff;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        text-align: center;
        >a>img{
          width: 150px;
          height: 150px;
        }
        .title{
          font-size: 14px;
          font-weight: 400;
        }
        .text{
          color: #b0b0b0;
        }
        .price{
          color: #ff6709;
          font-size: 14px;
          margin-top: 10px;
          margin-bottom: 15px;
        }
      }
    }
  }
}
</style>