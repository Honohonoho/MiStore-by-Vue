<template>
  <div class="hot-goods">
    <h2>热评产品</h2>
    <div class="container">
      <div class="wrapper">
        <div class="item" v-for="(item,index) in Items" :key="index"
            :class="{active: index === selected}"
            @mouseenter="selected = index" @mouseleave="selected = ''"
          >
          <a :href="item.link">
            <img :src="item.imgUrl">
          </a>
          <div class="content">
            <div class="commit">
              <p class="text">{{item.text}}</p>
              <p class="source">{{item.source}}</p>
            </div>
            <div class="info">
              <p class="title">{{item.title}}</p>
              <p class="price">{{item.price}}</p>
            </div>
          </div>
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
        {title: '小米胶囊耳机', text: '很小巧 像不喜欢戴活塞的人可以试试这种~很舒服包装还是一如既往的简洁 要是有盒子就好了=￣ω￣=', price: '69元', source: '来自于 鹤唳 的评价', imgUrl: './static/img/h-g-1.jpg', link: 'https://www.mi.com/capsuleearphone/'},
        {title: '小米路由器3', text: '安装简洁方便，信号不错！！！！！', price: '149元', source: '来自于 追逆 的评价', imgUrl: './static/img/h-g-2.jpg', link: 'https://www.mi.com/miwifi3/'},
        {title: '米家小白智能摄像机', text: '样子好可爱，特别是转来转去时很有趣。让它休眠时它就会把头转过去背对着你了，唤醒它又会自动转回来。你', price: '399元', source: '来自于 随风 的评价', imgUrl: './static/img/h-g-3.jpg', link: 'https://www.mi.com/micamera/'},
        {title: '小米净水器', text: '有了它，妈妈再也不用担心我喝不到健康的水了。呵呵，良心产品，平民价格，对现在的水质起到了很好的改善', price: '1299元', source: '来自于 爱疯911 的评价', imgUrl: './static/img/h-g-4.jpg', link: 'https://www.mi.com/water/'},
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.hot-goods{
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
        width: 296px;
        height: 415px;
        background: #fff;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
        text-align: center;
        >a>img{
          width: 296px;
          height: 220px;
        }
        .content{
          height: 190px;
          width: 240px;
          display: flex;
          flex-direction: column;
          justify-content: flex-start;
          align-items: center;
          color: #333;
          .commit{
            text-align: left;
            margin: 28px 0 15px 0;
            width: 240px;
            .text{
              font-size: 14px;
              font-weight: 400;
              line-height: 24px;
              height: 72px;
            }
            .source{
              color: #b0b0b0;
              margin: 22px 0 0 0;
            }
          }
          .info{
            display: flex;
            width: 240px;
            align-items: center;
            .title{
              font-size: 14px;
              font-weight: 400;
              padding-right: 10px;
              border-right: 2px solid #e0e0e0;
            }
            .price{
              color: #ff6709;
              padding-left: 10px;
              font-size: 14px;
            }
          }
        }
      }
    }
  }
}
</style>