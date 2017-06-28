<template>
  <div class="top-header">
    <div class="container">
      <a class="logo-mi"></a>
      <a class="gif"></a>
      <div class="header-nav" @mouseenter="isNavEnter = true" @mouseleave="isNavEnter = false">
        <ul>
          <li class="item" v-for="(item,index) in navItems" :key="index"
              :class="{active: item.type === selected}"
              @mouseenter="selected = item.type">
            <a href="#">{{item.name}}</a>
          </li>
        </ul>
      </div>
      <div class="header-search"
          @mouseenter="searchEnter"
          @mouseleave="searchLeave">
        <form>
          <input class="search-text" type="search" 
              @focus="inputFocus" @blur="inputBlur" 
              :class="{'search-focus': isFocus,'search-enter': isEnter}"
          >
          <label class="search-btn" value="" 
              :class="{'search-focus': isFocus,'search-enter': isEnter}"
          >
            <span class="icon"></span>
          </label>
        </form>
        <ul class="search-result" v-show="isFocus">
          <li v-for="(item,index) in results"  :key="index">
            <span class="item-name">{{item.name}}</span>
            <span class="item-num">约有{{item.number}}件</span>
          </li>
        </ul>
      </div>
    </div>
    <div class="header-menu" v-show="(selected !== '') && (isNavEnter || isMenuEnter)" @mouseenter="isMenuEnter = true" @mouseleave="isMenuEnter = false">
      <ul v-for="(item,index) in navItems" v-show="item.type === selected"  :key="index">
        <li v-for="(key,index) in tabItems[item.type]"  :key="index">
          <div class="product">
            <p class="info" >{{key.info}}</p>
            <a :href="key.link"><img :src="key.imgUrl" alt=""></a>
            <p class="title">{{key.title}}</p>
            <p class="price">{{key.price}}</p>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
// import $ from 'jQuery'
// import HeaderMenu from './HeaderMenu'

export default {
  data (){
    return {
      navItems: [
        {name: '小米手机', type: 'miphone'},
        {name: '红米', type: 'redmi'},
        {name: '平板 · 笔记本', type: 'pad'},
        {name: '电视', type: 'tv'},
        {name: '盒子 · 影音',type: 'box'},
        {name: '路由器', type: 'router'},
        {name: '智能硬件', type: 'hardware'},
        {name: '服务', type: ''},
        {name: '社区', type: ''}
      ],
      results: [
        {name: '小米手机5', number: '11'},
        {name: '空气净化器2', number: '1'},
        {name: '活塞耳机', number: '4'},
        {name: '小米路由器', number: '8'},
        {name: '移动电源', number: '21'},
        {name: '运动相机', number: '3'},
        {name: '小米摄像机', number: '2'},
        {name: '小米体重秤', number: '1'},
        {name: '小米插线板', number: '13'},
        {name: '配件优惠套装', number: '32'}
      ],
      tabItems: {
        miphone: [
          {title: '小米6', imgUrl: './static/img/xm6.png', link: 'https://www.mi.com/mi6/', price: '2499元起', info: '新品'},
          {title: '小米Max 2', imgUrl: './static/img/max2.png', link: 'https://www.mi.com/max2/', price: '1699元起', info: '新品'},
          {title: '小米Note 2', imgUrl: './static/img/xiaomiNOTE2.jpg', link: 'https://www.mi.com/minote2/', price: '2799元起', info: '现货'},
          {title: '小米MIX', imgUrl: './static/img/MIX.jpg', link: 'https://www.mi.com/mix/', price: '3499元起', info: '现货'},
          {title: '小米5s Plus', imgUrl: './static/img/5splus.jpg', link: 'https://www.mi.com/mi5splus/', price: '2299元起', info: '现货'},
          {title: '小米手机5c', imgUrl: './static/img/mi5c.png', link: 'https://www.mi.com/mi5c/', price: '1499元起', info: '现货'},
        ],
        redmi: [
          {title: '红米Note 4X', imgUrl: './static/img/hmn4x.jpg', link: 'https://www.mi.com/redminote4x/', price: '799元起', info: '新品'},
          {title: '红米4X', imgUrl: './static/img/hm4x.jpg', link: 'https://www.mi.com/redmi4x/', price: '699元起', info: '新品'},
          {title: '红米4A', imgUrl: './static/img/hm4a.png', link: 'https://www.mi.com/redmi4a/', price: '599元起', info: '新品'},
          {title: '红米4', imgUrl: './static/img/hm4.jpg', link: 'https://www.mi.com/redmi4', price: '799元起', info: '新品'},
        ],
        pad: [
          {title: '小米平板3 64GB', imgUrl: './static/img/mipad3.png', link: 'https://www.mi.com/mipad3/', price: '1499元', info: '新品'},
          {title: '小米笔记本Air 12.5', imgUrl: './static/img/bijiben12.5.jpg', link: 'https://www.mi.com/mibookair-12/', price: '3599元', info: '新品'},
          {title: '小米笔记本Air 13.3', imgUrl: './static/img/bijiben13.3.jpg', link: 'https://www.mi.com/mibookair/', price: '4999元', info: '新品'}
        ],
        tv: [
          {title: '小米电视4 49英寸', imgUrl: './static/img/xmds_49.png', link: 'https://www.mi.com/mitv4/49/', price: '3499元', info: '新品'},
          {title: '小米电视4 55英寸', imgUrl: './static/img/xmds_55.png', link: 'https://www.mi.com/mitv4/55/', price: '3999元起', info: '新品'},
          {title: '小米电视4 65英寸', imgUrl: './static/img/xmds_65.png', link: 'https://www.mi.com/mitv4/65/', price: '9999元', info: '新品'},
          {title: '小米电视4A 43英寸', imgUrl: './static/img/xmds4a_43.png', link: 'https://www.mi.com/mitv4A/43/', price: '2099元', info: '新品'},
          {title: '小米电视4A 49英寸', imgUrl: './static/img/xmds4a_49.png', link: 'https://www.mi.com/mitv4A/49/', price: '2599元', info: '新品'}
        ],
        box: [
          {title: '小米盒子3s', imgUrl: './static/img/mihezi.png', link: 'https://www.mi.com/mibox3s/', price: '299元', info: '新品'},
          {title: '小米盒子3c', imgUrl: './static/img/mihezi3c.png', link: 'https://www.mi.com/mibox3c/', price: '199元', info: '新品'},
          {title: '小米盒子3 增强版', imgUrl: './static/img/hezi3s.jpg', link: 'https://www.mi.com/hezi3s/', price: '399元', info: '新品'},
          {title: '小米家庭影院', imgUrl: './static/img/jiatingyingyuan.png', link: 'https://www.mi.com/misurround/', price: '1999元', info: '新品'},
          {title: '小米家庭音响 标准版', imgUrl: './static/img/yinxiang.jpg', link: 'https://item.mi.com/1160800074.html', price: '699元', info: '新品'}
        ],
        router: [
          {title: '小米路由器 HD/Pro', imgUrl: './static/img/HD-Pro.png', link: 'https://www.mi.com/miwifihd/', price: '499元起', info: '新品'},
          {title: '小米路由器 3G', imgUrl: './static/img/3G.png', link: 'https://www.mi.com/miwifi3g/', price: '249元', info: '新品'},
          {title: '小米路由器 3', imgUrl: './static/img/xmlyq3.png', link: 'https://www.mi.com/miwifi3/', price: '149元起', info: '新品'},
          {title: '小米路由器 3C', imgUrl: './static/img/3C.png', link: 'https://www.mi.com/miwifi3c/', price: '99元', info: '新品'},
          {title: '小米WiFi电力猫', imgUrl: './static/img/cilimao.png', link: 'https://www.mi.com/plc/', price: '249元', info: '新品'},
          {title: '小米WiFi放大器 2', imgUrl: './static/img/fdq2.jpg', link: 'https://item.mi.com/1164700010.html', price: '49元', info: '新品'}
        ],
        hardware: [
          {title: '小米体脂秤', imgUrl: './static/img/tzc.jpg', link: 'https://www.mi.com/scale2/', price: '199元', info: '新品'},
          {title: '小米手环2', imgUrl: './static/img/sh2.png', link: 'https://www.mi.com/shouhuan2/', price: '149元', info: '新品'},
          {title: '小米净水器', imgUrl: './static/img/jsqcs.png', link: 'https://www.mi.com/water3/', price: '1499元起', info: '新品'},
          {title: '小米VR眼镜 PLAY2', imgUrl: './static/img/xmvrplay2.png', link: 'https://www.mi.com/mivr2c/', price: '99元', info: '新品'},
          {title: '米家IH电饭煲', imgUrl: './static/img/dfb.jpg', link: 'https://www.mi.com/dianfanbao2/', price: '399元', info: '新品'},
        ]
      },
      selected: '',
      isFocus: false,
      isEnter: false,
      isNavEnter: false,
      isMenuEnter: false
    }
  },
  methods: {
    inputFocus: function(){
      this.isFocus = true
    },
    inputBlur: function(){
      this.isFocus = false
    },
    searchEnter: function(){
      this.isEnter = true
    },
    searchLeave: function(){
      this.isEnter = false
    }
  },
  components: {
  }
}
</script>

<style lang="scss" scoped>
.top-header{
  width: 100%;
  position: relative;
  >.container{
    width: 1226px;
    height: 100px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
    >.logo-mi{
      width: 55px;
      height: 55px;
      background: url(../assets/logo-mi.png) no-repeat;
    }
    >.gif{
      width: 163px;
      height: 66px;
      margin-left: 20px;
      background: url(../assets/win.gif) no-repeat;
    }
    >.header-nav{
      margin-right: auto;
      height: 100px;
      display: flex;
      align-items: center;
      ul{
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        .item>a{
          height: 66px;
          line-height: 66px;
          padding: 0 10px;
          font-size: 16px;
          &:hover{
            color: #ff6700;
          }
        }
      }
    }
    >.header-search{
      position: relative;
      form{
        height: 50px;
        display: flex;
        align-items: center;
        .search-text{
          width: 223px;
          height: 50px;
          padding: 0 10px;
          border: 1px solid #e0e0e0;
          border-right: none;
          font-size: 14px;
          line-height: 48px;
          outline: 0;
          transition: all .2s;
        }
        .search-enter{
        border-color: #333;
        }
        .search-btn{
          width: 52px;
          height: 48px;
          border: 1px solid #e0e0e0;
          font-size: 24px;
          line-height: 24px;
          background: #fff;
          color: #616161;
          outline: 0;
          transition: all .2s;
          cursor: pointer;
          display: flex;
          justify-content: center;
          align-items: center;
          >.icon{
            background: url(../assets/icon-search.png)  no-repeat;
            display: inline-block;
            width: 20px;
            height: 20px;
            background-size: 100% 100%;
            transition: all 0.2s;
          }
          &:hover{
            background: #ff6700;
            >.icon{
              background: url(../assets/icon-search-white.png)  no-repeat;
              display: inline-block;
              width: 20px;
              height: 20px;
              background-size: 100% 100%;
            }
          }
        }
        .search-enter{
        border-color: #b0b0b0;
        }
        .search-focus{
          border-color: #ff6700;
        }
      }
      .search-result{
        position: absolute;
        z-index: 3;
        box-sizing: border-box;
        top: 50px;
        width: 224px;
        border: 1px solid #ff6700;
        border-top: 0;
        background: #fff;
        li{
          padding: 7px 13px;
          color: #424242;
          cursor: pointer;
          display: flex;
          justify-content: space-between;
          align-items: center;
          .item-num{
            color: #b0b0b0;
          }
          &:hover{
            color: #ff6700;
          }
        }
      }
    }
  }
}

.header-menu{
  position: absolute;
  top: 100px;
  left: 0;
  right: 0;
  height: 230px;
  z-index: 6;
  background: #fff;
  border-top: 1px solid #e0e0e0;
  border-bottom: 1px solid #e0e0e0;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.15);
  >ul{
    display: flex;
    justify-content: flex-start;
    >li{
      width: 160px;
      padding: 0 10px;
      &:first-child{
        margin-left: 80px;
      }
      &:last-child>.product>a{
        border-right: 0;
      }
      .product{
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;
        >a{
          border-right: 1px solid #e0e0e0;
          padding-right: 10px;
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
