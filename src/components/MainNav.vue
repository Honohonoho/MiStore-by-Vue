<template>
  <div class="main-nav">
    <div class="nav-first" @mouseenter="isNavEnter = true" @mouseleave="isNavEnter = false">
      <ul>
        <li v-for="(item,index) in navFirst" :key="index"
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
        @mouseenter="isMenuEnter = true" @mouseleave="isMenuEnter = false">
      <ul v-for="(item,index) in navFirst" v-show="item.type === selected" :key="index">
        <li v-for="(key,index) in navSec[item.type]"  :key="index">
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
          {title: '小米移动电源', imgUrl: './static/img/dianyuan.jpg', link: 'https://www.mi.com/dianyuan/'},
          {title: '插线板', imgUrl: './static/img/c1xb.jpg', link: 'https://list.mi.com/125'},
          {title: '品牌移动电源', imgUrl: './static/img/yidongdianyuan.jpg', link: 'https://list.mi.com/13'},
          {title: '移动电源附件', imgUrl: './static/img/dianyuanfujian.jpg', link: 'https://list.mi.com/dyfj'},
          {title: '充电器', imgUrl: './static/img/chongdianqi.jpg', link: 'https://list.mi.com/15'},
          {title: '彩虹5号电池', imgUrl: './static/img/5Battery.jpg', link: 'https://item.mi.com/1154300033.html'},
          {title: '彩虹7号电池', imgUrl: './static/img/7Battery.jpg', link: 'https://item.mi.com/1155000010.html'},
        ],
        earphone: [
          {title: '小米头戴式耳机', imgUrl: './static/img/toudai.jpg', link: 'https://www.mi.com/miwifihd/'},
          {title: '头戴式耳机轻松版', imgUrl: './static/img/toudai.jpg', link: 'https://www.mi.com/miwifi3g/'},
          {title: '小米降噪耳机', imgUrl: './static/img/xmjzej.jpg', link: 'https://www.mi.com/miwifi3/'},
          {title: '小米圈铁耳机 Pro', imgUrl: './static/img/xmjzej.jpg', link: 'https://www.mi.com/miwifi3c/'},
          {title: '小米圈铁耳机', imgUrl: './static/img/xmjzej.jpg', link: 'https://www.mi.com/plc/'},
          {title: '小米胶囊耳机', imgUrl: './static/img/xmjzej.jpg', link: 'https://item.mi.com/1164700010.html'},
          {title: '小米活塞耳机清新版', imgUrl: './static/img/xmjzej.jpg', link: 'https://www.mi.com/scale2/'},
          {title: '小米蓝牙耳机', imgUrl: './static/img/xmjzej.jpg', link: 'https://www.mi.com/shouhuan2/'},
          {title: '小米运动蓝牙耳机', imgUrl: './static/img/xmjzej.jpg', link: 'https://www.mi.com/water3/'},
          {title: '品牌耳机', imgUrl: './static/img/toudai.jpg', link: 'https://www.mi.com/mivr2c/'},
          {title: '小米网络音响', imgUrl: './static/img/wlyx.jpg', link: 'https://www.mi.com/dianfanbao2/'},
          {title: '小米蓝牙音箱', imgUrl: './static/img/wlyx.jpg', link: 'https://www.mi.com/dianfanbao2/'},
          {title: '小米随身蓝牙音箱', imgUrl: './static/img/wlyx.jpg', link: 'https://www.mi.com/dianfanbao2/'},
          {title: '小钢炮音箱 2', imgUrl: './static/img/wlyx.jpg', link: 'https://www.mi.com/dianfanbao2/'},
          {title: '小米方盒子蓝牙音箱2', imgUrl: './static/img/wlyx.jpg', link: 'https://www.mi.com/dianfanbao2/'},
          {title: '小米方盒子蓝牙音箱', imgUrl: './static/img/wlyx.jpg', link: 'https://www.mi.com/dianfanbao2/'},
          {title: '小米音乐闹钟', imgUrl: './static/img/naozhong.jpg', link: 'https://www.mi.com/dianfanbao2/'},
          {title: '小米米兔音箱', imgUrl: './static/img/naozhong.jpg', link: 'https://www.mi.com/dianfanbao2/'},
          {title: '音乐蓝牙车充', imgUrl: './static/img/naozhong.jpg', link: 'https://www.mi.com/dianfanbao2/'}
        ],
        protect: [
          {title: '贴膜', imgUrl: './static/img/tiemo.jpg', link: 'https://list.mi.com/9'},
          {title: '保护套/保护壳', imgUrl: './static/img/baohu.jpg', link: 'https://list.mi.com/8'}
        ],
        card: [
          {title: '线材', imgUrl: './static/img/xiancai.jpg', link: 'https://list.mi.com/16'},
          {title: '自拍杆', imgUrl: './static/img/zipaigan.jpg', link: 'https://search.mi.com/search_%E8%87%AA%E6%8B%8D%E6%9D%86'},
          {title: '手机支架', imgUrl: './static/img/zhijia.jpg', link: 'https://list.mi.com/5'},
          {title: '存储卡', imgUrl: './static/img/cunchu.jpg', link: 'https://list.mi.com/27'}
        ],
        bag: [
          {title: '箱包', imgUrl: './static/img/xiangbao.jpg', link: 'https://list.mi.com/23'},
          {title: '90分旅行箱', imgUrl: './static/img/lvxingxiang.jpg', link: 'https://search.mi.com/search_%E6%97%85%E8%A1%8C%E7%AE%B1'},
          {title: '服饰', imgUrl: './static/img/huise.jpg', link: 'https://list.mi.com/22'},
          {title: '米家运动鞋 智能版', imgUrl: './static/img/ydx.jpg', link: 'https://search.mi.com/search_%E8%BF%90%E5%8A%A8%E9%9E%8B'},
          {title: 'TS 尼龙偏光太阳镜', imgUrl: './static/img/tyj.jpg', link: 'https://www.mi.com/ts-sunglasses/'}
        ],
        live: [
          {title: '米兔玩偶', imgUrl: './static/img/mitu.jpg', link: 'http://mitu.mi.com/'},
          {title: '生活周边', imgUrl: './static/img/zhoubian.jpg', link: 'https://list.mi.com/24'},
          {title: '《小米》会刊', imgUrl: './static/img/zazhi.jpg', link: 'https://www.mi.com/zazhi/index.html?1021'},
          {title: '毛巾/浴巾', imgUrl: './static/img/mj.jpg', link: 'https://search.mi.com/search_%E6%9C%80%E7%94%9F%E6%B4%BB'},
          {title: '8H乳胶床品', imgUrl: './static/img/rjcd.jpg', link: 'https://search.mi.com/search_%E4%B9%B3%E8%83%B6'}
        ]
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.main-nav{
  font-size: 14px;
  width: 1226px;
  background: #fff;
  margin: 0 auto;
  position: relative;
  display: flex;
  justify-content: flex-start;
  >.nav-first{
    width: 235px;
  	height: 458px;
    position: relative;
    z-index: 5;
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
    height: 458px;
    width: 992px;
    position: absolute;
    top: 0;
    right: 0;
    background: #fff;
    z-index: 5;
    overflow: hidden;
    border: 1px solid #e0e0e0;
    border-left: none;
    box-shadow: 0 8px 16px rgba(0,0,0,0.18);
    ul{
      height: 458px;
      display: flex;
      flex-flow: wrap;
      flex-direction: column;
      align-items: flex-start;
      align-content: flex-start;
      justify-content: flex-start;
      li{
        width: 265px;
        height: 76px;
        .product{
          a{
            display: flex;
            justify-content: flex-start;
            align-items: center;
            transition: color .2s;
            width: 265px;
            padding: 20px 20px;
            &:hover{
              color: #ff6700;
            }
            img{
              width: 40px;
              height: 40px;
              margin-right: 12px;
            }
          }
        }
      }
    }
  }
}
</style>