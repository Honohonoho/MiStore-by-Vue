<template>
  <div class="top-header">
    <div class="container">
      <a class="logo-mi"></a>
      <a class="gif"></a>
      <div class="header-nav">
        <ul>
          <li class="item" v-for="item in navItems">
            <a href="#">{{item.name}}</a>
          </li>
        </ul>
      </div>
      <div class="header-search">
        <form>
          <input class="search-text" type="search" name="keyword">
          <input class="search-btn" type="submit" value="">
        </form>
      </div>
    </div>  
  </div>
</template>

<script>
export default {
  data (){
    return {
      navItems: [
        {'name': '小米手机'},
        {'name': '红米'},
        {'name': '平板·笔记本'},
        {'name': '电视'},
        {'name': '盒子·影音'},
        {'name': '路由器'},
        {'name': '智能硬件'},
        {'name': '服务'},
        {'name': '社区'},
      ]
    }
  },

}
</script>

<style lang="scss" scoped>
.top-header{
  width: 100%;
  margin: 10px 0;
  >.container{
    width: 1226px;
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
        .search-btn{
          width: 52px;
          height: 50px;
          border: 1px solid #e0e0e0;
          font-size: 24px;
          line-height: 24px;
          background: #fff;
          color: #616161;
          outline: 0;
          transition: all .2s;
          cursor: pointer;
        }
      }
    }
  }
}
</style>
