<template>
  <div class="mi-content">
    <h2>内容</h2>
    <div class="container">
      <div class="wrapper">
        <div class="item" v-for="(item,index) in Items" :key="index"
            :class="{active: index === selected}"
            @mouseenter="selected = index" @mouseleave="selected = ''"
          >
          <a class="content" :href="item.link">
            <p class="type">{{item.type}}</p>
            <p class="title">{{item.title}}</p>
            <p class="text">{{item.text}}</p>
            <p class="price">{{item.price}}</p>
          </a>
          <a class="pic" :href="item.link">
            <img :src="item.imgUrl">
          </a>
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
        {title: '哈利·波特与被诅咒的孩子', text: '“哈利·波特”第八个故事中文版震撼来袭！特别彩排版剧本！', price: '29.37元', type: '图书', imgUrl: './static/img/m-c-1.png', link: 'http://www.duokan.com/book/120800'},
        {title: '几何', text: '最新官方主题，带你感受极简视觉冲击', price: '免费', type: 'MIUI 主题', imgUrl: './static/img/m-c-2.jpg', link: 'http://zhuti.xiaomi.com/detail/49ad623b-21ca-4b5c-82d4-1003dd1501b4'},
        {title: '米柚手游模拟器', text: '在电脑上玩遍小米所有手游', price: '免费', type: '游戏', imgUrl: './static/img/m-c-3.png', link: 'http://game.xiaomi.com/miyou/index.html'},
        {title: '小米应用', text: '小米出品 必属精品', price: '免费', type: '应用', imgUrl: './static/img/m-c-4.png', link: 'http://app.mi.com/subject/167924'},
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.mi-content{
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
        height: 420px;
        background: #fff;
        border-top: 1px solid #ffac13;
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;
        text-align: center;
        &:nth-child(2){
          border-color: #83c44e;
          .content>.type{
            color: #83c44e;
          }
        }
        &:nth-child(3){
          border-color: #e53935;
          .content>.type{
            color: #e53935;
          }
        }
        &:nth-child(4){
          border-color: #2196f3;
          .content>.type{
            color: #2196f3;
          }
        }
        >.pic>img{
          width: 216px;
          height: 154px;
        }
        .content{
          height: 190px;
          width: 240px;
          margin-bottom: 10px;
          display: flex;
          flex-direction: column;
          justify-content: flex-start;
          align-items: center;
          color: #333;
          .text{
            width: 200px;
            font-size: 12px;
            line-height: 20px;
            height: 40px;
            color: #b0b0b0;
          }
          .price{
            font-size: 14px;
            margin: 10px 0 0 0;
          }
          .title{
            font-size: 20px;
            font-weight: 400;
            line-height: 1.25;
            margin-bottom: 5px;
          }
          .type{
            color: #ffac13;
            font-size: 16px;
            font-weight: 400;
            padding: 45px 0 18px 0;
          }
        }
      }
    }
  }
}
</style>