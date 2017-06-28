<template>
  <div class="household-appliances">
    <h2>家电</h2>
    <div class="h-a-container">
      <div class="wrapper-left" :class="{ active: isMouseEnter}"
          @mouseenter="isMouseEnter = true" @mouseleave="isMouseEnter = false"
        >
        <a href="https://www.mi.com/water3/">
          <img :src="pic_1">
        </a>
      </div>
      <div class="wrapper-right">
        <div class="h-a-item" v-for="(item,index) in Items" :key="index"
            :class="{active: index === selected}"
            @mouseenter="selected = index" @mouseleave="selected = ''"
          >
          <a :href="item.link">
            <img :src="item.imgUrl">
          </a>
          <p class="title">{{item.title}}</p>
          <p class="text">{{item.text}}</p>
          <p class="price">{{item.price}}</p>
          <transition-group name="commit-slide" class="commit-slide" tag="div">
            <div class="commit" v-if="selected === index" :key="index">
              <p class="text">{{commits.text}}</p>
              <p class="source">{{commits.source}}</p>
            </div>
          </transition-group>
        </div>
        <div class="h-a-item item-exrta">
          <div class="item">
            <a href="https://www.mi.com/roomrobot/">
              <p>
                <span class="title">米家扫地机器人</span>
                <span class="price">1699元</span>
              </p>
              <img :src="pic_2">
            </a>
          </div>
          <div class="item more">
            <a href="https://www.mi.com/buytv/">
              <p>
                <span class="title">浏览更多</span>
                <span class="text">热门</span>
              </p>
              <img :src="pic_3">
            </a>
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
      isMouseEnter: false,
      selected: '',
      pic_1: './static/img/h-a-left.jpg',
      pic_2: './static/img/h-a-r-8.jpg',
      pic_3: './static/img/right.png',
      Items: [
        {title: '小米电视4A 43英寸', text: '2GB+8GB大存储，内置海量大片', price: '2099元', imgUrl: './static/img/h-a-r-1.png', link: 'https://item.mi.com/1170900021.html'},
        {title: '小米电视4 55英寸', text: '4.9mm超薄机身，无边框设计', price: '3999元', imgUrl: './static/img/h-a-r-2.jpg', link: 'https://item.mi.com/1171600035.html'},
        {title: '小米笔记本Air 13.3英寸', text: '独立显卡，全金属机身，超长续航', price: '4999元', imgUrl: './static/img/h-a-r-3.jpg', link: 'https://item.mi.com/product/10000061.html'},
        {title: '小米笔记本Air 12.5英寸', text: '独立显卡，全金属机身，超长续航', price: '3599元', imgUrl: './static/img/h-a-r-4.jpg', link: 'https://item.mi.com/product/10000032.html'},
        {title: '米家空气净化器Pro', text: 'OLED显示屏幕，激光颗粒物传感器', price: '1499元', imgUrl: './static/img/h-a-r-5.jpg', link: 'https://www.mi.com/airpro/'},
        {title: '米家压力IH电饭煲', text: '智能烹饪，灰铸铁粉体涂层内胆', price: '999元', imgUrl: './static/img/h-a-r-6.jpg', link: 'https://www.mi.com/dianfanbao/'},
        {title: 'Yeelight LED 吸顶灯', text: '5分钟快装，月光夜灯，IP60 级防尘', price: '359元', imgUrl: './static/img/h-a-r-7.png', link: 'https://www.mi.com/yeelight-ceilinglamp/'}
      ],
      commits: {text: '昨天刚收到，电视超一流，超好物流也快，雨天也不担务，...', source: '来自于 翔 的评价'}
    }
  }
}
</script>

<style lang="scss">
.household-appliances{
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
  .h-a-container{
    display: flex;
    justify-content: space-between;
    >.active{
      box-shadow: 0 15px 30px rgba(0,0,0,0.1);
      margin-top: -1px;
      transition: all .2s linear;
    }
    .wrapper-left{
      height: 614px;
      width: 234px;
    }
    .wrapper-right{
      width: 992px;
      height: 614px;
      color: #333;
      display: flex;
      flex-flow: wrap;
      justify-content: center;
      align-content: space-between;
      .active{
        box-shadow: 0 15px 30px rgba(0,0,0,0.1);
        margin-top: -1px;
        transition: all .2s linear;
      }
      .h-a-item{
        position: relative;
        overflow: hidden;
        height: 300px;
        width: 234px;
        margin-left: 14px;
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
          margin-top: 10px;
          margin-bottom: 15px;
        }
        .price{
          color: #ff6709;
          font-size: 14px;
        }
        .commit{
          position: absolute;
          z-index: 2;
          // bottom: 0px;
          left: 0;
          height: 90px;
          width: 234px;
          display: flex;
          flex-direction: column;
          justify-content: center;
          align-items: center;
          text-align: left;
          background: #ff6700;
          transform: translateY(-50%);
          .text{
            color: #fff;
            width: 174px;
          }
          .source{
            color: rgba(255,255,255,0.6);
            width: 174px;
          }
        }
      }
      .item-exrta{
        background: #f5f5f5;
        justify-content: space-between;
        overflow: visible;
        .item{
          height: 143px;
          width: 234px;
          background: #fff;
          display: flex;
          justify-content: space-around;
          align-items: center;
          transition: all .2s linear;
          &:hover{
            box-shadow: 0 15px 30px rgba(0,0,0,0.1);
            margin-top: -1px;
          }
          a{
            width: 234px;
            display: flex;
            justify-content: space-around;
            p{
              display: flex;
              flex-direction: column;
              justify-content: center;
              text-align: left;
              .title{
                text-overflow: ellipsis;
                white-space: nowrap;
                overflow: hidden;
                margin-bottom: 14px;
              }
            }
            img{
              width: 80px;
              height: 80px;
            }
          }
        }
        .more>a>img{
          width: 62px;
          height: 60px;
          margin-left: 20px;
        }
        .more .title{
          font-size: 18px;
        }
        .more .text{
          margin: 0;
        }
      }
    }
  }
}
//commit-slide动画
.commit-slide-enter-active,.commit-slide-leave-active{
  transition: all .2s linear;
  bottom: -50px;
  opacity: 1;
}
.commit-slide-enter,.commit-slide-leave-to/* .fade-leave-active in <2.1.8 */ {
  bottom: -90px;
  opacity: 0;
  transition: all .2s linear;
}
</style>


