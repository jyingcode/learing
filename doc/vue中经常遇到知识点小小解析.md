### 数据绑定

-   数据绑定最常见的形式就是使用 {{...}}（双大括号）的文本插值：

```
	<h3>{{ comment }}</h3>
<script>
new Vue({
  el: '#app',
  data: {
    comment: '加辣'
  }
})
</script>
```

### 循环语句用 v-for 指令

-   v-for 指令需要以 site in sites 形式的特殊语法， sites 是源数据数组并且 site 是数组元素迭代的别名。
    v-for 可以绑定数据到数组来渲染一个列表：

```
<li class="list-item" v-for="(item, index) in list" :key="index">
    <h3>{{ item.menu }}</h3>
    <span>{{ item.date }}</span>
    <span>{{ item.comment }}</span>
    <span>{{ item.price }}</span>
</li>

<script>
new Vue({
  el: '#app',
	data() {
		return {
			item: {
				img: 'xxx',
				menu: '',
				comment: '',
				price: '',
			},
        }
	},
})
</script>
```

### 计算属性 computed。

-   计算属性在处理一些复杂逻辑和获取数据时是很有用的.
    比如获取 Vuex 中数据:

```
<script>
import { mapState } from 'vuex'

export default {
    computed: {
		...mapState({
			list: (state) => state.app.list,
			loading: (state) => state.app.loading,
		}),
	},
}
</script>
```

### 监听属性 watch

-   可以通过 watch 来响应数据的变化。

```
<div>
<p> name:{{ setName}}</p>
<p> Getname<input type="text" v-model = "getName"></p>
</div>
new Vue({
  el: '#app',
  data: {
    getName: 'zhangsan',
    lastName: 'lisi',
    setName: ''
  },
  watch: {
    firstName(newName, oldName) {
      this.setName = newName + ' ' + this.lastName;
    }
  }
})
```

### 样式绑定

-   class 与 style 是 HTML 元素的属性，用于设置元素的样式，我们可以用 v-bind 来设置样式属性。
    Vue.js v-bind 在处理 class 和 style 时， 专门增强了它。表达式的结果类型除了字符串之外，还可以是对象或数组。

```
<ul class="list-box">
        <button v-bind:class="{ active: isActive === 1 }" @click="jump('/index')">首页</button>
        <button v-bind:class="{ active: isActive === 3 }" @click="jump('/add')">添加订单</button>
      </ul>
<style>
.list-box{
  float: left;
  width: 200px;
  height: 100%;
  border: 2px solid #d8d8d8;
  border-top: 0;
  padding-top:10px
}
.list-box button{
  width:100px;
  height: 30px;
  border-radius: 5px;
  background-color:#d8d8d8;
  margin-top:10px;
  border:none;
  outline: none;
}
</style>
```

### 事件处理器

-   事件监听可以使用 v-on 指令，也可以@

```
<button v-on:click="counter += 1">增加 1</button>
 <button v-bind:class="{ active: isActive === 1 }" @click="jump()">首页</button>
```

### 表单

-   可以用 v-model 指令在表单控件元素上创建双向数据绑定。

```
<el-form-item label="图片" prop="img">
		<el-input
			v-model="formData.img"
			placeholder="请输入内容">
        </el-input>
</el-form-item>
```

### 组件

-   Component 是 Vue.js 最强大的功能之一。
    组件可以扩展 HTML 元素，封装可重用的代码。
    组件系统让我们可以用独立可复用的小组件来构建大型应用，几乎任意类型的应用的界面都可以抽象为一个组件树：
    注册组件

```
<script>
import Nav from '../Nav'
import Siderbar from '../Siderbar'
export default {
	name: 'App',
	components: {
		Nav,
		Siderbar,
	},
}
</script>
```

使用组件

```
<template>
	<div>
		<Nav />
		<div class="main">
			<Siderbar />
			<div class="content">
				<router-view />
			</div>
		</div>
	</div>
</template>
```

-   在 Vue 中，父子组件的关系可以总结为 prop 向下传递，事件向上传递。父组件通过 prop 给子组件下发数据，子组件通过事件给父组件发送信息。

1. 给组件绑定数据，子组件 props 接收

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

-   子组件\$emit 向父组件传数据@click="click"

```
click() {
 this.$emit('childFn', this.data);
        }
```

###
