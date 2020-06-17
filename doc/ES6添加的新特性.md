#### 自己开发中遇到次数相对较多的 ES6 新特性，小小总结一下，大佬勿喷，还请多多指教。

### 定义变量 let 和 const

#### let

1. let 声明的变量不具备变量提升
2. let 用于声明局部变量，是块级作用域
3. let 不允许重复声明的
4. 紧紧是全局变量和 window 没有声明关系
5. 通常用得多的是在 for 循环中

```
var arr = [1,2,3,45,]
for(let i = 0; i < arr.length;i++){
	console.log(arr[i])
}
```

#### const

1. const 声明的变量不可以修改，也就是不能修改 const 声明的指向了
2. const 也不具备变量提升
3. const 声明一个对象，对象所包含的值是可以被修改的。换一句话来说，只要对象指向的地址不被修改，就是允许的

```
const  people = {
    name:"zhangsan",
    age:"25"
    }
people.age = 28 //可以
```

### 箭头函数

1. 不需要用关键字 function 来定义函数；
2. 一般只有一个参数的情况下可以省略 return；

```
var arr = [1,2,3,4,5]
var result = arr.map(e => e * 2)
 console.log(result)
```

3. 在箭头函数内部，this 并不会跟其他函数一样指向调用它的对象，而是继承上下文的 this 指向的对象。

### 扩展运算符（...）

1. 将字符串解构成数组

```
var str = " hello"
console.log([...str])
//['h','e','l','l','o']
```

2. 数组合并

```
const arr = [...[1,2,3],...[4,5]]
console.log(arr)
//[1,2,3,4,5]
```

3. 函数调用

```
function add (x,y){
     return x + y
}
var fn = add(7,13)
console.log(fn)
//20
```

### 新增对 String,Array,Object 一些操作方法

#### String

1. 经常用到 includes，如果当前字符串包含被搜寻的字符串，就返回 true,否则返回 false。

```
var str = "hello world name age"
console.log(str.includes("hello"))
//true
console.log(str.includes("Array"))
// false
```

#### Array

1. Array.of 将一组数值转化为数组

```
Array.of(7)
// [7]
Array.of(1, 2, 3)
// [1, 2, 3]
```

#### Object

1. Object.assign()用来合并对象

```
var obj1 = {a:1}
var obj2 = {b:2}
var obj3 = {c:3}
var obj = Object.assign(obj1,obj2,obj3)
console.log(obj)
//{
    a:1,
    b:2,
    c:3
}
```

### Promise

1. 异步操作的同步代码
2. promise 的基本使用通过 new promise 创建一个 promise 对象里面有一个参数，参数是一个回调函数，回调函数中有 2 个参数，resolve，reject,resolve()当异步执行成功的时候调用的方法，reject()当异步失败的时候调用的方法。除此之外 promise 有一个 then 方法，当成功的时候执行第一个回调函数，当失败的时候执行第二个回调函数。第二个回调函数也可以通过 promise 对象.catch 调用
3. Promise.all():当所有的异步代码都执行完毕以后才会执行.then 中的操作
4. Promise.race():只要有一个 promise 执行完毕后就会执行.then 操作

5. 可以通过 new premise 实例通过定时器 setTimeout 实现多个异步同步执行

```
new Promise(function(resolve){
	setTimeout(function(){
　　　　 console.log('1');
　　　　     resolve()
		 }).then(function(){
		     console.log('2')
			})

```
