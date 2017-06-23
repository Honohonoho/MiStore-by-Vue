<template>
  <div class="top-container">
    <div class="top-bar">
      <div class="topbar-nav">
        <ul>
          <li class="item" v-for="item in navItems">
            <a href="#">{{item.name}}</a>
          </li>
        </ul>
      </div>
      <div class="topbar-info">
        <a href="#">登录</a>
        <a href="#">注册</a>
      </div>
      <div class="topbar-cart">
        <a href="#">购物车（<span>0</span>）</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function(){
    return{
      navItems: [
        {'name': '小米商城'},
        {'name': 'MIUI'},
        {'name': '米聊'},
        {'name': '游戏'},
        {'name': '多看阅读'},
        {'name': '云服务'},
        {'name': '金融'},
        {'name': '小米网移动版'},
        {'name': '问题反馈'},
        {'name': 'Select Region'},
      ]
    }
  },
  methods: {

  },
  components: {

  }
}
</script>

<style lang="scss" scoped>
.top-container{
  width: 100%;
  background: #333;
  >.top-bar{
    width: 1226px;
    height: 40px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
    >.topbar-nav{
      >ul{
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        >.item{
          padding: 0 .5em;
          border-right: 1px solid #424242;
          &:last-child{
          border: none;
          }
          & a{
            color: #b0b0b0;
            &:hover{
            color: #fff;
            }
          }
        }
      }
    }
    >.topbar-info{
      margin-left: 500px;
      >a{
        color: #b0b0b0;
        padding: 0 .5em;
        border-right: 1px solid #424242;
        &:last-child{
        border: none;
        }
        &:hover{
          color: #fff;
        }
      }
    }
    >.topbar-cart{
      >a{
        color: #b0b0b0;
        padding: 0 .5em;
        border-right: 1px solid #424242;
        &:last-child{
        border: none;
        }
        &:hover{
          color: #fff;
        }
      }
    }
  }
}
</style>

