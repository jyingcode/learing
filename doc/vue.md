### vue是什么
- 是一套构建用户界面的渐进式框架
1.生命周期的作用
- 生命周期有多个事件钩子，让控制整个Vue实例的过程时更容易，逻辑更清晰
2. 什么是生命周期
- Vue实例从创建到销毁到过程
3.生命周期有哪些
- 创建
*beforecreate前created后
- 挂载
* beforemount前mounted后*
- 更新
* beforeupdata前updataed后*
- 销毁
* beforeDestroy前Destoryed后*
### MVVM
1. model:数据类型
2. view:UI组件
3. viewmodle:监听数据的改变和控制视图，处理用户交互，同步view和modle的对象
### 计算属性
- computed:{}
- 模块中把数据绑定到一个计算属性上，Vue会在其依赖的任何值上导致计算属性的改变时更新Dom
### Vuex
- 专门为Vue服务的管理数据仓库，用于管理页面的数据
- 通过在全局注册store对象，来实现组件间的状态共享
- Vuex提供数据的操作方式
1. getter
- {辅助函数mapgetter}
- import{mapgetter}form "路径"
```
computed: {
  foo () {
return this.$store.state.data
  }
}
```
2. mutation
- {辅助函数mapmutation}
```
const mutations = {
 SET_LIST: (s,v) => {
   s.list = v
 },
```
1. commit
- 同步操作
```
this.$store.commit('SET_LIST',friend);*储存*
```
- 取值
```
this.$store.state.SET_LIST;
```
2. dispatch
- 异步操作
```
this.$store.dispatch('SET_LISt',friend);*储存*
```
- 取值
```
this.$store.state.getter.SET_LIST;
``` 
3. action
- {辅助函数mapaction}
```
const actions = {
  setList ({commit}, list) {
    console.log
    commit('SET_LIST', list)
  }
}
```
*任何组件都可以在Vuex中存取数据*

### 组件传参
1. 父组件
- 给组件绑定数据，子组件props 接收
```
export default {
  props: {
    title: {
      default: 'hello world'
    }
  }
}
```
2. 子组件
- 子组件$emit传父组件@click=click
```
click() {
 this.$emit('childFn', this.data);
        }
```
### vue指令有哪些常见的
1. v-if
- v-if后面赋予 可以转化为布尔类型的表达式(true)(false)
2. v-show
- 用display:none控制元素的的隐藏和显示
3. v-bind
- v-bind指令可以在其名称后面带一个参数，中间放一个冒号隔开，这个参数通常是HTML元素的特性
4. v-else
- 和v-if使用如果v-if为false就运行v-elae
5. v-for
- 父元素用v-for可以遍历子元素中的Array|object|string
6. v-model
- 数据双向绑定
7. v-on
- 事件监听
### v-if和v-show区别
- v-if控制Dom节点的显示隐藏v-show控制元素的隐藏和显示