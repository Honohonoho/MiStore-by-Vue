<template>
  <div class="main-nav">
    <div class="nav-first" @mouseenter="isNavEnter = true" @mouseleave="isNavEnter = false">
      <ul>
        <li v-for="item in navFirst"
            :class="{active: item.type === selected}"
            @mouseenter="selected = item.type">
          <p>
            <span>{{item.name}}</span>
            <span class="icon">></span>
          </p>
        </li>
      </ul>
    </div>
    <div class="nav-sec" v-show="isNavEnter || isMenuEnter"
        @mouseenter="isMenuEnter = true" @mouseleave="isMenuEnter = false"
    >
      <ul v-for="item in navFirst" v-show="item.type === selected">
        <li v-for="key in navSec[item.type]">
          <div class="product">
            <a :href="key.link">
              <img :src="key.imgUrl" alt="">
              <p class="title">{{key.title}}</p>
            </a>
          </div>
        </li>
      </ul>
    </div>

  </div>
</template>

<script>
export default {
  data(){
    return {
      selected: '',
      isNavEnter: false,
      isMenuEnter: false,
      navFirst: [
        {name: '手机 电话卡', type: 'phone'}, 
        {name: '笔记本 平板', type: 'pad'}, 
        {name: '电视 盒子', type: 'tv'},
        {name: '路由器 智能硬件', type: 'router'}, 
        {name: '移动电源 电池 插线板', type: 'charger'}, 
        {name: '耳机 音箱', type: 'earphone'},
        {name: '保护套 贴膜', type: 'protect'}, 
        {name: '线材 支架 存储卡', type: 'card'}, 
        {name: '箱包 服饰 鞋 眼镜', type: 'bag'}, 
        {name: '米兔 生活周边', type: 'live'}
      ],
      navSec: {
        phone: [
          {title: '小米6', imgUrl: './static/img/xm6.png', link: 'https://www.mi.com/mi6/'},
          {title: '小米Max 2', imgUrl: './static/img/max2.png', link: 'https://www.mi.com/max2/'},
          {title: '小米Note 2', imgUrl: './static/img/xiaomiNOTE2.jpg', link: 'https://www.mi.com/minote2/'},
          {title: '小米MIX', imgUrl: './static/img/MIX.jpg', link: 'https://www.mi.com/mix/'},
          {title: '小米5s Plus', imgUrl: './static/img/5splus.jpg', link: 'https://www.mi.com/mi5splus/'},
          {title: '小米手机5c', imgUrl: './static/img/mi5c.png', link: 'https://www.mi.com/mi5c/'},
          {title: '红米Note 4X', imgUrl: './static/img/hmn4x.jpg', link: 'https://www.mi.com/redminote4x/'},
          {title: '红米4X', imgUrl: './static/img/hm4x.jpg', link: 'https://www.mi.com/redmi4x/'},
          {title: '红米4A', imgUrl: './static/img/hm4a.png', link: 'https://www.mi.com/redmi4a/'},
          {title: '红米4', imgUrl: './static/img/hm4.jpg', link: 'https://www.mi.com/redmi4'}
        ],
        pad: [
          {title: '小米平板3 64GB', imgUrl: './static/img/mipad3.png', link: 'https://www.mi.com/mipad3/'},
          {title: '小米笔记本Air 12.5', imgUrl: './static/img/bijiben12.5.jpg', link: 'https://www.mi.com/mibookair-12/'},
          {title: '小米笔记本Air 13.3', imgUrl: './static/img/bijiben13.3.jpg', link: 'https://www.mi.com/mibookair/'}
        ],
        tv: [
          {title: '小米电视4 49英寸', imgUrl: './static/img/xmds_49.png', link: 'https://www.mi.com/mitv4/49/'},
          {title: '小米电视4 55英寸', imgUrl: './static/img/xmds_55.png', link: 'https://www.mi.com/mitv4/55/'},
          {title: '小米电视4 65英寸', imgUrl: './static/img/xmds_65.png', link: 'https://www.mi.com/mitv4/65/'},
          {title: '小米电视4A 43英寸', imgUrl: './static/img/xmds4a_43.png', link: 'https://www.mi.com/mitv4A/43/'},
          {title: '小米电视4A 49英寸', imgUrl: './static/img/xmds4a_49.png', link: 'https://www.mi.com/mitv4A/49/'},
          {title: '小米盒子3s', imgUrl: './static/img/mihezi.png', link: 'https://www.mi.com/mibox3s/'},
          {title: '小米盒子3c', imgUrl: './static/img/mihezi3c.png', link: 'https://www.mi.com/mibox3c/'},
          {title: '小米盒子3 增强版', imgUrl: './static/img/hezi3s.jpg', link: 'https://www.mi.com/hezi3s/'},
          {title: '小米家庭影院', imgUrl: './static/img/jiatingyingyuan.png', link: 'https://www.mi.com/misurround/'},
          {title: '小米家庭音响 标准版', imgUrl: './static/img/yinxiang.jpg', link: 'https://item.mi.com/1160800074.html'}
        ],
        router: [
          {title: '小米路由器 HD/Pro', imgUrl: './static/img/HD-Pro.png', link: 'https://www.mi.com/miwifihd/'},
          {title: '小米路由器 3G', imgUrl: './static/img/3G.png', link: 'https://www.mi.com/miwifi3g/'},
          {title: '小米路由器 3', imgUrl: './static/img/xmlyq3.png', link: 'https://www.mi.com/miwifi3/'},
          {title: '小米路由器 3C', imgUrl: './static/img/3C.png', link: 'https://www.mi.com/miwifi3c/'},
          {title: '小米WiFi电力猫', imgUrl: './static/img/cilimao.png', link: 'https://www.mi.com/plc/'},
          {title: '小米WiFi放大器 2', imgUrl: './static/img/fdq2.jpg', link: 'https://item.mi.com/1164700010.html'},
          {title: '小米体脂秤', imgUrl: './static/img/tzc.jpg', link: 'https://www.mi.com/scale2/'},
          {title: '小米手环2', imgUrl: './static/img/sh2.png', link: 'https://www.mi.com/shouhuan2/'},
          {title: '小米净水器', imgUrl: './static/img/jsqcs.png', link: 'https://www.mi.com/water3/'},
          {title: '小米VR眼镜 PLAY2', imgUrl: './static/img/xmvrplay2.png', link: 'https://www.mi.com/mivr2c/'},
          {title: '米家IH电饭煲', imgUrl: './static/img/dfb.jpg', link: 'https://www.mi.com/dianfanbao2/'}
        ],
        charger: [
          {title: '小米路由器 HD/Pro', imgUrl: './static/img/HD-Pro.png', link: 'https://www.mi.com/miwifihd/'},
          {title: '小米路由器 3G', imgUrl: './static/img/3G.png', link: 'https://www.mi.com/miwifi3g/'},
          {title: '小米路由器 3', imgUrl: './static/img/xmlyq3.png', link: 'https://www.mi.com/miwifi3/'},
          {title: '小米路由器 3C', imgUrl: './static/img/3C.png', link: 'https://www.mi.com/miwifi3c/'},
          {title: '小米WiFi电力猫', imgUrl: './static/img/cilimao.png', link: 'https://www.mi.com/plc/'},
          {title: '小米WiFi放大器 2', imgUrl: './static/img/fdq2.jpg', link: 'https://item.mi.com/1164700010.html'},
          {title: '小米体脂秤', imgUrl: './static/img/tzc.jpg', link: 'https://www.mi.com/scale2/'},
          {title: '小米手环2', imgUrl: './static/img/sh2.png', link: 'https://www.mi.com/shouhuan2/'},
          {title: '小米净水器', imgUrl: './static/img/jsqcs.png', link: 'https://www.mi.com/water3/'},
          {title: '小米VR眼镜 PLAY2', imgUrl: './static/img/xmvrplay2.png', link: 'https://www.mi.com/mivr2c/'},
          {title: '米家IH电饭煲', imgUrl: './static/img/dfb.jpg', link: 'https://www.mi.com/dianfanbao2/'}
        ],
        earphone: [
          {title: '小米路由器 HD/Pro', imgUrl: './static/img/HD-Pro.png', link: 'https://www.mi.com/miwifihd/'},
          {title: '小米路由器 3G', imgUrl: './static/img/3G.png', link: 'https://www.mi.com/miwifi3g/'},
          {title: '小米路由器 3', imgUrl: './static/img/xmlyq3.png', link: 'https://www.mi.com/miwifi3/'},
          {title: '小米路由器 3C', imgUrl: './static/img/3C.png', link: 'https://www.mi.com/miwifi3c/'},
          {title: '小米WiFi电力猫', imgUrl: './static/img/cilimao.png', link: 'https://www.mi.com/plc/'},
          {title: '小米WiFi放大器 2', imgUrl: './static/img/fdq2.jpg', link: 'https://item.mi.com/1164700010.html'},
          {title: '小米体脂秤', imgUrl: './static/img/tzc.jpg', link: 'https://www.mi.com/scale2/'},
          {title: '小米手环2', imgUrl: './static/img/sh2.png', link: 'https://www.mi.com/shouhuan2/'},
          {title: '小米净水器', imgUrl: './static/img/jsqcs.png', link: 'https://www.mi.com/water3/'},
          {title: '小米VR眼镜 PLAY2', imgUrl: './static/img/xmvrplay2.png', link: 'https://www.mi.com/mivr2c/'},
          {title: '米家IH电饭煲', imgUrl: './static/img/dfb.jpg', link: 'https://www.mi.com/dianfanbao2/'}
        ],
        protect: [
          {title: '小米路由器 HD/Pro', imgUrl: './static/img/HD-Pro.png', link: 'https://www.mi.com/miwifihd/'},
          {title: '小米路由器 3G', imgUrl: './static/img/3G.png', link: 'https://www.mi.com/miwifi3g/'}
        ],
        card: [
          {title: '小米路由器 HD/Pro', imgUrl: './static/img/HD-Pro.png', link: 'https://www.mi.com/miwifihd/'},
          {title: '小米路由器 3G', imgUrl: './static/img/3G.png', link: 'https://www.mi.com/miwifi3g/'},
          {title: '小米路由器 3', imgUrl: './static/img/xmlyq3.png', link: 'https://www.mi.com/miwifi3/'},
          {title: '小米路由器 3C', imgUrl: './static/img/3C.png', link: 'https://www.mi.com/miwifi3c/'}
        ],
        bag: [
          {title: '小米路由器 HD/Pro', imgUrl: './static/img/HD-Pro.png', link: 'https://www.mi.com/miwifihd/'},
          {title: '小米路由器 3G', imgUrl: './static/img/3G.png', link: 'https://www.mi.com/miwifi3g/'},
          {title: '小米路由器 3', imgUrl: './static/img/xmlyq3.png', link: 'https://www.mi.com/miwifi3/'},
          {title: '小米路由器 3C', imgUrl: './static/img/3C.png', link: 'https://www.mi.com/miwifi3c/'},
          {title: '小米WiFi电力猫', imgUrl: './static/img/cilimao.png', link: 'https://www.mi.com/plc/'}
        ],
        live: [
          {title: '小米路由器 HD/Pro', imgUrl: './static/img/HD-Pro.png', link: 'https://www.mi.com/miwifihd/'},
          {title: '小米路由器 3G', imgUrl: './static/img/3G.png', link: 'https://www.mi.com/miwifi3g/'},
          {title: '小米路由器 3', imgUrl: './static/img/xmlyq3.png', link: 'https://www.mi.com/miwifi3/'},
          {title: '小米路由器 3C', imgUrl: './static/img/3C.png', link: 'https://www.mi.com/miwifi3c/'},
          {title: '小米WiFi电力猫', imgUrl: './static/img/cilimao.png', link: 'https://www.mi.com/plc/'}
        ]
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.main-nav{
  font-size: 14px;
  display: flex;
  justify-content: flex-start;
  >.nav-first{
    width: 235px;
  	height: 458px;
    ul{
      display: flex;
      justify-content: space-between;
      flex-direction: column;
      background: rgba(0,0,0,0.6);
      padding: 20px 0;
      color: #fff;
      li{
        padding-left: 30px;
        height: 42px;
        line-height: 42px;
        cursor: pointer;
        &:hover{
          background: #ff6700;
        }
        >p{
          display: flex;
          justify-content: space-between;
          >.icon{
            margin-right: 20px;
            font-weight: bold;
          }
        }
      }
    }
  }
  .nav-sec{
    position: relative;
    width: 795px;
    height: 458px;
    border: 1px solid #e0e0e0;
    box-shadow: 0 8px 16px rgba(0,0,0,0.18);
    ul{
      position: absolute;
      left: 0;
      top: 0;
      display: flex;
      flex-flow: wrap;
      justify-content: flex-start;
      li{
        width: 265px;
        height: 76px;
        .product{
          display: flex;
          justify-content: flex-start;
          a{
            img{
              width: 40px;
              height: 40px;
            }
          }
        }
      }
    }
  }
}
</style>