# 使用Vue.js完成小米官方商城页面
![](http://upload-images.jianshu.io/upload_images/5548587-af70ee6f6cb6be46.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
# 前言
经历了上一个动手实践的项目，重复性，机械性，低效率的编写经历，使我开始思考如何提高敲代码的效率及代码的质量，使用框架去编写页面的这个想法便应运而生，然数种成熟的框架对于我这种选择困难症星人造成了成吨的伤害。。。
     
     
经过一番斟酌，最终选择了Vue.js，幸好之前用React做过一个To-Do应用，所以上手Vue.js时，尽管踩了许多坑，但是解决和debug的过程不再毫无头绪，无从下手。（笑~）
# 使用的技术
完成这个项目的初衷是为了熟悉Vue.js的语法和常见的API，所以并没有用vue-router或vuex，深入学习之后会考虑吧。。。    

**1. vue-cli**     

    之前学习React时用了react-creat-app，所以这次用vue-cli工具，    
    来初始化一个 vue 项目，省去了配置各种文件的烦恼，真是贴心~用法见下↓    

``` 
npm install -g vue-cli  //安装
vue init webpack .      //初始化
```   

**2. webpack**     

    由于 vue-cli 其实也是用了 webpack，所以用起来不会特别陌生。    

**3. scss**    

    之前我写的样式都是 CSS，为了提高效率就加上了 CSS 预处理（别问我为什么不用LESS...）    

```npm install --save  sass-loader node-sass```    

**4. Vue**    

    怎么说呢，请看文章标题。

# 目录结构
```
...
|—— build                  //build 目录用于存放构建脚本，如 webpack 配置文件
├── config                 //config 目录用于存放一些配置信息，比如配置打包后的 bundle 文件存放在哪里
|—— dist                   //存放编译打包好的文件运行npm run build会生成
    |—— static             //build之后，线上部署时的静态资源
    |—— index.html         //线上部署时的首页
|—— node_modules           //安装的依赖
|—— src                    //除了首页，其他的源代码都在 src 目录里
    |—— assets             //组件静态资源库
    |—— components         //相关组件
    |—— router             //路由配置
    |—— App.vue            //主组件
    |—— main.js            //JS 入口文件
├── static                 //static 目录用于放置静态资源，比如 favicon.ico 文件等
|—— test                   //单元测试等代码放在 test 目录里
├── README.md
|── index.html             //开发环境的首页，运行npm run dev,在本地创建一个服务器 
├── package.json    
```
使用Vue Devtools查看组件结构:     

![](http://upload-images.jianshu.io/upload_images/5548587-5a6123b28a4f0e09.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
# 运行步骤
```
# 安装依赖
npm install

# 在本地启动服务，并且通过localhost:8080地址进行访问
npm run dev

# 编译并且压缩代码
npm run build
```
# 界面预览
[在线预览](https://honohonoho.github.io/MiStore-by-Vue/dist/#/)     

[GitHub地址](https://github.com/Honohonoho/MiStore-by-Vue)    

PC端:    

![](http://upload-images.jianshu.io/upload_images/5548587-af70ee6f6cb6be46.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
移动端:    

![](http://upload-images.jianshu.io/upload_images/5548587-3c6ec24c3a729796.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
# 后记
这个项目前前后后用了不到6天的时间，因为自己习惯在开始一个Project前先画个草图构思一下，再把官方文档浏览了一遍，所以遇到需求时，知道要去文档哪一章找方法，正所谓，磨刀不误砍柴工嘛~
   
   
使用Vue开发这个项目的过程中，心路历程是这样的：这个animate不错==>这个animate怎么写==>看完文档后==>还能这样写。踩的坑基本都是这个套路，不过习惯了Vue的中心思想后，对列表渲染，条件渲染，常见的事件绑定，模板语法，过度效果，LifeCycle，基本的响应式原理都有了亲身体会，也算是有了进步。
    
    
看看时间，要抓紧时间找工作了，上海或杭州求个前端的坑。
邮箱：751718620@qq.com
    
    
李祺 ---2017年6月