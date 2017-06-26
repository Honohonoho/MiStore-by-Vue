<template>
  <div class="header-menu">
    <ul>
      <li v-for="item in miphone">
        <div class="product">
          <p class="info">{{item.info}}</p>
          <a :href="item.link"><img :src="item.imgUrl" alt=""></a>
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
        {title: '小米6', imgUrl: './static/img/xm6.png', link: 'https://www.mi.com/mi6/', price: '2499元起', info: '新品'},
        {title: '小米Max 2', imgUrl: './static/img/max2.png', link: 'https://www.mi.com/max2/', price: '1699元起', info: '新品'},
        {title: '小米Note 2', imgUrl: './static/img/xiaomiNOTE2.jpg', link: 'https://www.mi.com/minote2/', price: '2799元起', info: '现货'},
        {title: '小米MIX', imgUrl: './static/img/MIX.jpg', link: 'https://www.mi.com/mix/', price: '3499元起', info: '现货'},
        {title: '小米5s Plus', imgUrl: './static/img/5splus.jpg', link: 'https://www.mi.com/mi5splus/', price: '2299元起', info: ''},
        {title: '小米手机5c', imgUrl: './static/img/mi5c.png', link: 'https://www.mi.com/mi5c/', price: '1499元起', info: ''},
      ],
     	redmi: [
				{title: '红米Note 4X', imgUrl: './static/img/hmn4x.jpg', link: 'https://www.mi.com/redminote4x/', price: '799元起'},
				{title: '红米4X', imgUrl: './static/img/hm4x.jpg', link: 'https://www.mi.com/redmi4x/', price: '699元起'},
				{title: '红米4A', imgUrl: './static/img/hm4a.png', link: 'https://www.mi.com/redmi4a/', price: '599元起'},
				{title: '红米4', imgUrl: './static/img/hm4.jpg', link: 'https://www.mi.com/redmi4', price: '799元起'},
			],
			pad: [
				{title: '小米平板3 64GB', imgUrl: './static/img/mipad3.png', link: 'https://www.mi.com/mipad3/', price: '1499元'},
				{title: '小米笔记本Air 12.5', imgUrl: './static/img/bijiben12.5.jpg', link: 'https://www.mi.com/mibookair-12/', price: '3599元'},
				{title: '小米笔记本Air 13.3', imgUrl: './static/img/bijiben13.3.jpg', link: 'https://www.mi.com/mibookair/', price: '4999元'}
			],
			tv: [
				{title: '小米电视4 49英寸', imgUrl: './static/img/xmds_49.png', link: 'https://www.mi.com/mitv4/49/', price: '3499元'},
				{title: '小米电视4 55英寸', imgUrl: './static/img/xmds_55.png', link: 'https://www.mi.com/mitv4/55/', price: '3999元起'},
				{title: '小米电视4 65英寸', imgUrl: './static/img/xmds_65.png', link: 'https://www.mi.com/mitv4/65/', price: '9999元'},
				{title: '小米电视4A 43英寸', imgUrl: './static/img/xmds4a_43.png', link: 'https://www.mi.com/mitv4A/43/', price: '2099元'},
				{title: '小米电视4A 49英寸', imgUrl: './static/img/xmds4a_49.png', link: 'https://www.mi.com/mitv4A/49/', price: '2599元'}
			],
			box: [
				{title: '小米盒子3s', imgUrl: './static/img/mihezi.png', link: 'https://www.mi.com/mibox3s/', price: '299元'},
				{title: '小米盒子3c', imgUrl: './static/img/mihezi3c.png', link: 'https://www.mi.com/mibox3c/', price: '199元'},
				{title: '小米盒子3 增强版', imgUrl: './static/img/hezi3s.jpg', link: 'https://www.mi.com/hezi3s/', price: '399元'},
				{title: '小米家庭影院', imgUrl: './static/img/jiatingyingyuan.png', link: 'https://www.mi.com/misurround/', price: '1999元'},
				{title: '小米家庭音响 标准版', imgUrl: './static/img/yinxiang.jpg', link: 'https://item.mi.com/1160800074.html', price: '699元'}
			],
			router: [
				{title: '小米路由器 HD/Pro', imgUrl: './static/img/HD-Pro.png', link: 'https://www.mi.com/miwifihd/', price: '499元起'},
				{title: '小米路由器 3G', imgUrl: './static/img/3G.png', link: 'https://www.mi.com/miwifi3g/', price: '249元'},
				{title: '小米路由器 3', imgUrl: './static/img/xmlyq3.png', link: 'https://www.mi.com/miwifi3/', price: '149元起'},
				{title: '小米路由器 3C', imgUrl: './static/img/3C.png', link: 'https://www.mi.com/miwifi3c/', price: '99元'},
				{title: '小米WiFi电力猫', imgUrl: './static/img/cilimao.png', link: 'https://www.mi.com/plc/', price: '249元'},
				{title: '小米WiFi放大器 2', imgUrl: './static/img/fdq2.jpg', link: 'https://item.mi.com/1164700010.html', price: '49元'}
			],
			hardware: [
				{title: '小米体脂秤', imgUrl: './static/img/tzc.jpg', link: 'https://www.mi.com/scale2/', price: '199元'},
				{title: '小米手环2', imgUrl: './static/img/sh2.png', link: 'https://www.mi.com/shouhuan2/', price: '149元'},
				{title: '小米净水器', imgUrl: './static/img/jsqcs.png', link: 'https://www.mi.com/water3/', price: '1499元起'},
				{title: '小米VR眼镜 PLAY2', imgUrl: './static/img/xmvrplay2.png', link: 'https://www.mi.com/mivr2c/', price: '99元'},
				{title: '米家IH电饭煲', imgUrl: './static/img/dfb.jpg', link: 'https://www.mi.com/dianfanbao2/', price: '399元'},
			],
      currentPage: this.miphone
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

<style lang="scss" scoped>
.header-menu{
  position: absolute;
  bottom: 0;
  left: 0;
  width: 1226px;
  transform: translate(0,100%);
  height: 230px;
  overflow: hidden;
  z-index: 3;
  background-color: white;
  border-top: 1px solid #e0e0e0;
  border-bottom: 1px solid #e0e0e0;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.15);
  >ul{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 3;
    background: white;
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
