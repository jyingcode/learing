-   深拷贝和浅考都是对复杂对象的操作

```
var obj = {
     name: "zhangsan"
     age: ["26","30"]
     person:{
        man:"26",
     }
}
```

### 深拷贝

-   另外在堆内存中占用一块单独堆内存存放数据，内容和原来的对象一样,更改原来的对象，深拷贝的对象不会改变。
-   实现深拷贝用得比较多的方法是 JSON.parse(JSON.stringify())

```
var obj = {
				nama: 'zhangsan',
				age: ['25', '26'],
			}
			const obj1 = JSON.parse(JSON.stringify(obj))
			obj1.nama = 'zhaosi'
			obj1.age[1] = '30'
			console.log(obj, obj1)
```

{nama: "zhangsan", age: Array(2)}age: Array(2)0: "25"1: "26"
{nama: "zhaosi", age: Array(2)}age: (2) ["25", "30"]nama: "zhaosi"

### 浅拷贝

-   只拷贝对象的引用，（对象的”引用值“也可以是属性为引用类型）当原对象引用发生改变，拷贝的对象也发生变化。

```
var shallowCopy = (obj) => {
				const result = {}
				for (let key in obj) {
					if (obj.hasOwnProperty(key)) {
						result[key] = obj[key]
					}
				}
				return result
			}
			const start = {
				name: 'zhangsan',
				age: 25,
				friend: {
					name: 'lisi',
				},
			}
			const foo = shallowCopy(start)
			foo.friend.name = 'zhaosi'
			console.log(start)
```

{name: "zhangsan", age: 25, friend: {…}}
age: 25
friend:
name: "zhaosi"
**proto**: Object
name: "zhangsan"
