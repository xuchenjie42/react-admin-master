## 基于React+antd实现后台模板
自己利用业余时间，基于React+antd写了一个后台管理模板。主要是熟悉antd组件和React，页面主要还是展示页面,比较简单不涉及后台交互。

github地址：[基于React+antd实现后台模板](https://github.com/zhangZhiHao1996/react-admin-master)  
预览地址：[预览地址](https://zhangzhihao1996.github.io/react-admin-master/)
<br/>

### 技术栈

 - react
 - antd
 - react-router
 - mobx
 - canvas
 - ES6
 - cookie

自己参考了其他优秀的插件，比如[动态打字效果](https://blog.csdn.net/qq_37860930/article/details/80859473)、背景粒子效果、[shuffle（洗牌）](https://github.com/Vestride/Shuffle)，[全屏插件](https://github.com/sindresorhus/screenfull.js)等，自己对有些插件封装成类使用

所有路由都需要登录才可进入，自己封装了PrivateRoute组件来实现路由认证，登录信息保存在cookie中，原本是保存在store中，但是刷新页面后登录状态丢失，所以就保存在cookie中
登录背景图太大，使用了[TinyPNG](https://tinypng.com/)进行压缩，并编写了一个loading效果
<br/>

### 项目目录结构

<img src="https://github.com/zhangZhiHao1996/image-store/blob/master/react-admin-master/111.png?raw=true"/>
assets----存储静态图片资源和共用icon图标<br/>
components----存储共用组件<br/>
routes----业务页面入口和常用模板<br/> 
store----状态管理<br/>
utils----工具函数<br/>
<br/>

### 项目截图

<img src="https://github.com/zhangZhiHao1996/image-store/blob/master/react-admin-master/01.png?raw=true"/>  
<img src="https://github.com/zhangZhiHao1996/image-store/blob/master/react-admin-master/02.png?raw=true"/>  
<img src="https://github.com/zhangZhiHao1996/image-store/blob/master/react-admin-master/03.png?raw=true"/>  
<img src="https://github.com/zhangZhiHao1996/image-store/blob/master/react-admin-master/04.png?raw=true"/>  
<br/>

### 问题

整个demo不复杂，主要是熟悉react和路由等，在打包的过程中出现了一点小问题。我打包的文件是放在服务器二级目录下，所以打包的路径要改为相对路径，不能使用绝对路径，我在package.json中添加了homepage:'.'解决了路径问题。然后BrowserRouter加上了 basename=‘二级目录名称’ 属性，结果还是出现js路径错误，我一直以为是webpack打包的问题，找了很久才发现是因为BrowserRouter，将BrowserRouter改为HashRouter就访问正确。  
使用react-router（v4）时，如果有服务器端的动态支持，建议使用 BrowserRouter，否则建议使用 HashRouter。  
关于BrowserRouter和HashRouter的区别，可以参考：[关于 reactrouter 4.0版本中 BrowserRouter和HashRouter的问题](https://cnodejs.org/topic/5a193c5d6190c8912ebacd5d)、[react-router v4中 HashRouter 和 BrowserRouter的使用](https://www.cnblogs.com/sunLemon/p/9020153.html)
<br/>

### 最后
demo是我断断续续写的，只有下班和周末有时间。写demo的目的主要是熟悉React和react-router以及antd，整个demo中参考了一些其他人的想法，如动画效果等。另外基于vue的个人项目可以看这个[仿制移动端QQ音乐](https://blog.csdn.net/qq_37860930/article/details/80586698)

