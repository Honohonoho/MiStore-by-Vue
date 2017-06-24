<template>
  <div class="top-header">
    <div class="container">
      <a class="logo-mi"></a>
      <a class="gif"></a>
      <div class="header-nav">
        <ul>
          <li class="item" v-for="item in navItems"
              @mouseenter="navEnter">
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
          <li v-for="item in results">
            <span class="item-name">{{item.name}}</span>
            <span class="item-num">约有{{item.number}}件</span>
          </li>
        </ul>
      </div>
    </div>
    <transition name="menu-expand">
      <headerMenu v-show="isNavEnter" @mouseleave="navLeave"></headerMenu>
    </transition>  
  </div>
</template>

<script>
// import $ from 'jQuery'
import HeaderMenu from './HeaderMenu'

export default {
  data (){
    return {
      navItems: [
        {name: '小米手机'},
        {name: '红米'},
        {name: '平板 · 笔记本'},
        {name: '电视'},
        {name: '盒子 · 影音'},
        {name: '路由器'},
        {name: '智能硬件'},
        {name: '服务'},
        {name: '社区'}
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
      isFocus: false,
      isEnter: false,
      isNavEnter: false
    }
  },
  methods: {
    inputFocus: function(){
      // $('.search-text,.search-btn').addClass('search-focus')
      // $('.search-result').show()
      this.isFocus = true
    },
    inputBlur: function(){
      // $('.search-text,.search-btn').removeClass('search-focus')
      // $('.search-result').hide()
      this.isFocus = false
    },
    searchEnter: function(){
      this.isEnter = true
    },
    searchLeave: function(){
      this.isEnter = false
    },
    navEnter: function(){
      this.isNavEnter = true
    },
    navLeave: function(){
      this.isNavEnter = false
    }
  },
  components: {
    'headerMenu': HeaderMenu
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
      ul{
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        .item>a{
          height: 66px;
          line-height: 66px;
          padding: 0 10px;
          font-size: 16px;
          color: #333;
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
        box-sizing: border-box;
        top: 50px;
        width: 224px;
        border: 1px solid #ff6700;
        border-top: 0;
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
//HeaderMenu动画
.menu-expand-enter-active, .menu-expand-leave-active {
  transition: height .3s ease;
  height: 230px;
}
.menu-expand-enter,.menu-expand-leave-to/* .fade-leave-active in <2.1.8 */ {
  height: 0;
  transition: height .3s ease;
}
</style>
