### js五大数据类型
1. null
- 只有一个值的数据类型，就是null
2. string
- 为字符串表达类型
```
var String = "JavaScript"
```
3. undefined
- undefined值只有一个，就是声明对象但是没有对其赋值与初始化
4. Boolear
- 常用与条件判断，为true时运行那段代码，为false时运行那段代码,也可以用来判断DOM结点的显示隐藏
```
var list = true
* v-if：headDle = true 即当前headDle为显示*
var bar =false
* v-if：headDle = true 即当前headDle为隐藏*
```
5. number
- 为数字类型
### 数据的引用类型
1. Array
- 数组的每一项可以保存任何类型的数据。也就是说，可以用数组的第一个位置来保存字符串，用第二位置来保存数值，用第三个位置来保存对象
```
var Array = new Array()
```
2. Object
- 对象
```
var bar = new Object()
bar.list = "JavaScript";
bar.first = "Hi"
//或者//
var bar = {
    list: "javaScript",
    first: "Hi"
}
```
3. Function
- 函数的创建
```
var bar = function{}
bar (){}
```
### Js语句
1. if
- 判断语句，会把调用值转换成Boolear,如果调用值为true,则执行bar，如果调用值为false,则执行foo
```
var a = 10
if(a = 5){
    console.log(bar)
}else {
    console.log(foo)
}
```
2. do-while
3. for
- 循环语句，具有在执行循环之前初始化变量和定义循环后要执行的代码的能力
```
var count = 10
for(let i =0:i < count;i++){
    count[i]
}
```
4. swicth
- 判断循环语句
```
var count = [1,3,4,6,7,8]
switch (count) {
    case 1: bar
      break;
    case 3: bar
      break;
    case 4: bar
      break;
    case 6: bar
      break;
```
### Js函数
1. 函数的调用与传参
```
function sum(num1, num2) {
    return num1 + num2;
}
sum(10,20)
```