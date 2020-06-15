### computed计算属性：
```
<div id="app">
			<input type="text" v-model="name" />
			<input type="text" v-model="newName" />
			<input type="text" v-model="groupName" />
		</div>
		<script src="../js/vue.js"></script>
		<script>
			var app = new Vue({
				el: '#app',
				data: {
					name: '首都',
					newName: '北京',
				},
				computed: {
					groupName() {
						console.log(111)
						return this.name + '' + this.newName
					},
				},
			})
		</script>
```
1. 只要数据发生改变，就会重新进行计算
2. 如果computed属性属性值是函数，那么默认会走get方法；函数的返回值就是属性的属性值；
在computed中，属性都有一个get和一个set方法，当数据变化时，调用set方法
3. 不支持异步，当computed中有异步操作时无效，无法监听数据的变化。
### watch监听属性：
```
watch: {
    name: function (val) {
      this.groupName = val + ' ' +this.newName
    },
    newName: function (val) {
      this.groupName = this.name + '' + val
    }
  }
```
1. 支持异步操作
2. 数据变，会直接触发对应的操作
3. 监听函数会传入两个参数