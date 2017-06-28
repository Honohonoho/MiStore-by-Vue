<template>
  <footer>
    <div class="service">
      <a :href="item.link" v-for="(item,index) in service" :key="index">
        <span class="iconfont">{{item.unicode}}</span>
        <span class="text">{{item.text}}</span>
      </a>
    </div>
    <div class="link">
      <div class="item" v-for="(item,index) in link" :key="index">
        <span class="title">{{item.title}}</span>
        <a :href="key.link" v-for="(key,index) in item.text" :key="key">
          <span>{{key.title}}</span>
        </a>
      </div>
      <div class="contact">
        <span class="number">400-100-5678</span>
        <span class="text">周一至周日 8:00-18:00<br>（仅收市话费）</span>
        <span class="customer">24小时在线客服</span>
      </div>
    </div>
    <div class="info">
      <div class="info-container">
        <div class="mi-logo"><img src="../assets/logo-mi.png"></div>
        <div class="text">
          <p>小米商城|MIUI|米聊|多看书城|小米路由器|视频电话|小米天猫店|小米淘宝直营店|小米网盟|小米移动|隐私政策|Select Region</p>
          <p>©mi.com 京ICP证110507号 京ICP备10046444号 京公网安备11010802020134号 京网文[2014]0059-0009号 </p>
          <p>违法和不良信息举报电话：185-0130-1238，本网站所列数据，除特殊说明，所有数据均出自我司实验室测试</p>
        </div>
        <div class="info-logo">
          <img class="info-logo" src="../assets/info-logo-1.png">
          <img class="info-logo" src="../assets/info-logo-2.png">
          <img class="info-logo" src="../assets/info-logo-3.png">
          <img class="info-logo" src="../assets/info-logo-4.png">
        </div>
      </div>
    </div>
    <div class="slogan"><img src="../assets/slogan.png"></div>
  </footer>
</template>

<script>
export default {
  data(){
    return {
      service: [
        {text: '预约维修服务', unicode: '\ue6c4', link: 'https://www.mi.com/static/fast/'},
        {text: '7天无理由退货', unicode: '\ue776', link: 'https://www.mi.com/service/exchange#back'},
        {text: '15天免费换货', unicode: '\ue608', link: 'https://www.mi.com/service/exchange#free'},
        {text: '满150元包邮', unicode: '\ue609', link: 'https://www.mi.com/service/exchange#mail'},
        {text: '520余家售后网点', unicode: '\ue627', link: 'https://www.mi.com/static/maintainlocation/'}
      ],
      link: [
        {
          title: '帮助中心', 
          text: [
            {title: '账户管理', link: 'https://www.mi.com/service/account/register/'},
            {title: '购物指南', link: 'https://www.mi.com/service/buy/buytime/'},
            {title: '订单操作', link: 'https://www.mi.com/service/order/sendprogress/'}
          ]
        },
        {
          title: '服务支持', 
          text: [
            {title: '售后政策', link: 'https://www.mi.com/service/exchange'},
            {title: '自助服务', link: 'http://fuwu.mi.com/'},
            {title: '相关下载', link: 'http://xiazai.mi.com/'}
          ]
        },
        {
          title: '线下门店', 
          text: [
            {title: '小米之家', link: 'https://www.mi.com/c/xiaomizhijia/'},
            {title: '服务网点', link: 'https://www.mi.com/static/maintainlocation/'},
            {title: '零售网点', link: 'https://www.mi.com/static/familyLocation/'}
          ]
        },
        {
          title: '关于小米', 
          text: [
            {title: '了解小米', link: 'https://www.mi.com/about/'},
            {title: '加入小米', link: 'http://hr.xiaomi.com/'},
            {title: '联系我们', link: 'https://www.mi.com/about/contact/'}
          ]
        },
        {
          title: '关注我们', 
          text: [
            {title: '新浪微博', link: 'http://weibo.com/xiaomishangcheng'},
            {title: '小米部落', link: 'http://xiaoqu.qq.com/mobile/share/index.html?url=http%3A%2F%2Fxiaoqu.qq.com%2Fmobile%2Fbarindex.html%3Fwebview%3D1%26type%3D%26source%3Dindex%26_lv%3D25741%26sid%3D%26_wv%3D5123%26_bid%3D128%26%23bid%3D10525%26from%3Dwechat'},
            {title: '官方微信', link: 'https://www.mi.com/index.html#J_modalWeixin'}
          ]
        },
        {
          title: '特色服务', 
          text: [
            {title: 'F 码通道', link: 'https://order.mi.com/queue/f2code'},
            {title: '礼物码', link: 'https://www.mi.com/giftcode/'},
            {title: '防伪查询', link: 'https://order.mi.com/misc/checkitem'}
          ]
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
@font-face {
  font-family: 'iconfont';  /* project id 273742 */
  src: url('//at.alicdn.com/t/font_o29w1lx6rktn8kt9.eot');
  src: url('//at.alicdn.com/t/font_o29w1lx6rktn8kt9.eot?#iefix') format('embedded-opentype'),
  url('//at.alicdn.com/t/font_o29w1lx6rktn8kt9.woff') format('woff'),
  url('//at.alicdn.com/t/font_o29w1lx6rktn8kt9.ttf') format('truetype'),
  url('//at.alicdn.com/t/font_o29w1lx6rktn8kt9.svg#iconfont') format('svg');
}
.iconfont{
    font-family:"iconfont" !important;
    font-size:16px;font-style:normal;
    -webkit-font-smoothing: antialiased;
    -webkit-text-stroke-width: 0.2px;
    -moz-osx-font-smoothing: grayscale;
}
footer{
  display: flex;
  margin: 0 auto;
  flex-direction: column;
  justify-content: space-between;
  align-content: center;
  .service{
    width: 1226px;
    padding: 30px 0;
    margin-bottom: 30px;
    border-bottom: 1px solid #e0e0e0;
    background: #fff;
    display: flex;
    justify-content: center;
    >a{
      width: 240px;
      height: 25px;
      border-left: 1px solid #e0e0e0;
      font-size: 16px;
      line-height: 25px;
      color: #616161;
      display: flex;
      justify-content: center;
      align-items: center;
      transition: all .2s;
      &:hover{
        color: #ff6700;
      }
      &:nth-child(1){
        border: none;
      }
      .iconfont{
        font-size: 24px;
        margin-right: 5px;
      }
    }
  }
  .link{
    width: 1226px;
    margin: 0 auto;
    margin-bottom: 30px;
    display: flex;
    justify-content: space-between;
    .item{
      width: 160px;
      height: 112px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      >.title{
        margin: 0 0 26px;
        font-size: 14px;
        color: #424242;
      }
      >a{
        display: flex;
        align-items: center;
        transition: all .2s;
        color: #757575;
        &:hover{
          color: #ff6700;
        }
      }
    }
    .contact{
      width: 251px;
      height: 112px;
      border-left: 1px solid #e0e0e0;
      text-align: center;
      color: #616161;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      align-items: center;
      .number{
        margin: 0 0 5px;
        font-size: 22px;
        color: #ff6700;
      }
      .text{
        line-height: 16px;
      }
      .customer{
        background: #fff;
        color: #ff6700;
        width: 118px;
        height: 28px;
        line-height: 28px;
        border: 1px solid #ff6700;
        cursor: pointer;
        transition: all .2s;
        &:hover{
          background: #ff6700;
          color: #fff;
        }
      }
    }
  }
  .info{
    width: 100%;
    padding: 30px 0;
    font-size: 12px;
    background: #fafafa;
    .info-container{
      width: 1226px;
      margin: 0 auto;
      display: flex;
      justify-content: space-between;
      .mi-logo>img{
        width: 57px;
        height: 57px;
        margin-right: 10px;
      }
      .text{
        color: #b0b0b0;
        text-align: left;
        margin-right: auto;
        line-height: 18px;
        >p:nth-child(1){
          color: #757575;
        }
      }
      .info-logo{
        display: flex;
        justify-content: space-between;
        height: 28px;
      }
    }
  }
  .slogan{
    text-align: center;
    background: #fafafa;
    padding-bottom: 30px;
  }
}
</style>


