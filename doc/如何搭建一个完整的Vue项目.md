1. 首先，如果没有安装Node.js情况下先去Node.js官网下载安装Node.js
```
https://nodejs.org/en/
```
安装时直接安装在目录里面就行，安装完成时打开命令行输入
```
npm -v
```
查看当前Node.js版本看是否已经安装成功。
2. Node.js安装成功以后就用操作命令安装Vue-cli脚手架
```
# 最新稳定版
npm install vue
```
安装完会返回
```
whdeMac-mini:project windy$ npm install vue
+ vue@2.6.11
updated 1 package in 23.549s

40 packages are looking for funding
  run `npm fund` for details

```
3. 安装完成后操作命令创建项目
```
vue create '项目的名称'
```
输入vue create '项目的名称'会返回
```
whdeMac-mini:|自己本地文件目录| windy$ vue create 'article'
Vue CLI v4.3.1
? Please pick a preset: (Use arrow keys)
❯ default (babel, eslint) 
  Manually select features 
```
4. 项目创建完成后可以按自己需求来选择配置
5. 配置完成后会返回
```
$ cd article
$ npm run serve
```
命令行输入：
```
cd |项目名称|(跳转到项目名称下)
npm run serve
```
会返回
```
- Local:   http://localhost:8080/ 
  - Network: http://192.168.0.6:8080/
```
最后CTRL+鼠标左键点击http://localhost:8080/ 打开项目框架
6. 框架搭建完成就去项目的根目录下找到项目并打开找到src.main.js
```
import Vue from 'vue'
import App from './App.vue'

Vue.config.productionTip = false

new Vue({
  render: h => h(App),
}).$mount('#app')
```
7. 配置路由
- 首先在项目中安装路由
```
whdeMac-mini:article windy$ npm install router
+ router@1.3.5
added 5 packages from 7 contributors in 25.676s

44 packages are looking for funding
  run `npm fund` for details
```
完成安装后在scr创建一个router文件，在router下建index.js，在index.js引入配置路由
```
import Vue from 'vue'   //引入Vue
import Router from 'vue-router'  //引入vue-router
import Index from '../components/Content/Index'  //引入根目录下的Index组件
Vue.use(Router)  //Vue全局使用Router
 
export default new Router({
  routes: [              //配置路由，这里是个数组
    {                    //每一个链接都是一个对象
      path: '/index',         //链接路径
      name: 'index',     //路由名称，
      component:Index//对应的组件模板
    },
   
  ]
})
```
router配置好后在scr下的main.js引用：
```
import Vue from 'vue'
import App from './App.vue'
import router from './router';

Vue.config.productionTip = false

new Vue({
  router,
  render: h => h(App),
}).$mount('#app')
```
7. Vuex的配置在命令行输入npm install Vuex如下：
```
whdeMac-mini:article windy$ npm install vuex
+ vuex@3.4.0
added 1 package from 1 contributor in 17.067s

44 packages are looking for funding
  run `npm fund` for details

```
在src下创建一个store文件里面在建index.js和modules文件，modules下建一个app.js。
index.js的配置如下：
```
import Vue from 'vue'
import Vuex from 'vuex'
import app from './modules/app'

Vue.use(Vuex)
console.log(app)
const store = new Vuex.Store({
    modules: {
        app
    },
  // // getters
})

export default store
```
modules文件下的app.js如下：
```
const state = {
  
}

const mutations = {
  TOGGLE_SIDEBAR: state => {
    state.sidebar.opened = !state.sidebar.opened
    state.sidebar.withoutAnimation = false
  },
  CLOSE_SIDEBAR: (state, withoutAnimation) => {
    state.sidebar.opened = false
    state.sidebar.withoutAnimation = withoutAnimation
  },
  TOGGLE_DEVICE: (state, device) => {
    state.device = device
  },
  SET_SIZE: (state, size) => {
    state.size = size
  }
}

const actions = {
  
}

export default {
  state,
  mutations,
  actions
}
```
最后在src下的main.js中引用store:
```
import Vue from 'vue'
import App from './App.vue'
import router from './stroe';

Vue.config.productionTip = false

new Vue({
  stroe,
  render: h => h(App),
}).$mount('#app')
```
这样一个简单的Vue项目，vue-router，Vuex就完成了
