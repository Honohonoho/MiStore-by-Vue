<template>
  <div class="intelligence">
    <h2>智能</h2>
    <div class="intel-container">
      <div class="wrapper-left">
        <div class="left-item" v-for="(item,index) in wrapLeft" :key="index"
            :class="{active: index === selected_left}"
            @mouseenter="selected_left = index" @mouseleave="selected_left = ''"
          >
          <a :href="item.link">
            <img :src="item.imgUrl">
          </a>
        </div>
      </div>
      <div class="wrapper-right">
        <div class="right-item" v-for="(item,index) in Items" :key="index"
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
        <div class="right-item item-exrta">
          <div class="item">
            <a href="https://item.mi.com/1150500009.html">
              <p>
                <span class="title">小米千兆网线</span>
                <span class="price">14.9元</span>
              </p>
              <img :src="pic_2">
            </a>
          </div>
          <div class="item more">
            <a href="https://www.mi.com/smart/">
              <p>
                <span class="title">浏览更多</span>
                <span class="text">路由器</span>
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
      selected_left: '',
      pic_2: './static/img/intel-r-8.jpg',
      pic_3: './static/img/right.png',
      wrapLeft: [
        {imgUrl: './static/img/intel-l-1.jpg', link: 'https://www.mi.com/scooter/'},
        {imgUrl: './static/img/intel-l-2.jpg', link: 'https://www.mi.com/roomrobot/'}
      ],
      Items: [
        {title: '小米路由器3', text: '四天线设计，更快更强', price: '149元', imgUrl: './static/img/intel-r-1.jpg', link: 'https://www.mi.com/miwifi3/'},
        {title: '小米路由器3C', text: 'APP智能控制，安全防蹭网', price: '99元', imgUrl: './static/img/intel-r-2.jpg', link: 'https://www.mi.com/miwifi3c/'},
        {title: '小米WiFi放大器 2', text: '适配主流路由器，两步完成设置', price: '49元', imgUrl: './static/img/intel-r-3.jpg', link: 'https://item.mi.com/1164700010.html'},
        {title: '小米路由器 HD', text: '全新金属机身设计，4x4全向性天线', price: '1299元', imgUrl: './static/img/intel-r-4.jpg', link: 'https://www.mi.com/miwifihd/'},
        {title: '小米WiFi电力猫', text: '需要与路由器产品搭配使用', price: '249元', imgUrl: './static/img/intel-r-5.jpg', link: 'https://www.mi.com/plc/'},
        {title: '小米路由器 Pro', text: '全新金属机身设计，4x4全向性天线', price: '499元', imgUrl: './static/img/intel-r-6.jpg', link: 'https://www.mi.com/miwifihd/'},
        {title: '小米路由器3G', text: '双核全千兆设计，USB 3.0', price: '249元', imgUrl: './static/img/intel-r-7.jpg', link: 'https://item.mi.com/1171900014.html'}
      ],
      commits: {text: '昨天刚收到，电视超一流，超好物流也快，雨天也不担务，...', source: '来自于 翔 的评价'}
    }
  }
}
</script>

<style lang="scss" scoped>
.intelligence{
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
  .intel-container{
    display: flex;
    justify-content: space-between;
    .wrapper-left{
      height: 614px;
      width: 234px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      >.active{
        box-shadow: 0 15px 30px rgba(0,0,0,0.1);
        margin-top: -1px;
        transition: all .2s linear;
      }
      .left-item{
        height: 300px;
        width: 234px;
        a>img{
          height: 300px;
          width: 234px;
        }
      }
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
      .right-item{
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
            margin-top: 10px;
            margin-bottom: 15px;
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