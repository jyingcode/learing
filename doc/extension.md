### 数组的扩展
1. Array.from用于将两类对象转化成真正的数组
```
let Like = {
    '0':'a',
    '1':'b',
    '2':'c'
}
var arr = Array.from(Like)
console.log(arr)
```
* (...)扩展运算符也可以把一些数据结构转为数组*
- Array.from还可接受第二个参数，用来对每个元素进行处理，将处理过的值放入原数组
```
let Like = [1,2,3]
var arr2 = Array.from(Like,(x) =>x * x)
console.log(arr2)
```
2. Array.of将一组值转换为数组
```
var TheNumerical = 26
var TheNumerical1 = Array.of(TheNumerical)
console.log(TheNumerical1)
```
3. copyWithin()把当前数组指定位置的值复制到指定到位置
```
var arr2 = [1,2,3,4,5,6,7,8]
var arr3 = arr2.copyWithin(0,3)
console.log(arr3)
// [4,5,3,4,5,6,7,8]
var arr4 = [1,2,3,4,5]
var arr5 = arr4.copyWithin(0,3,4)
console.log(arr5)
//[4,2,3,4,5]
```
4. find()从数组中找到满足指定条件的值，直到找到，返回该值
```
var arr6 = [1,5,8,-9,15]
var arr7 = arr6.find((x) > 8 )
console.log(arr7)
```
5. findIndex()从数组中找到满足指定条件的值，直到找到，返回该值的索引
* value当前值，index当前位置，arr原数组*
```
var arr8 = [1,7,9,15]
var arr9 = arr8.findIndex(function(value,index,arr){
    return value > 9
})
console.log(arr9)
// 3
```
6. includes判断一个数组中是否有指定的值。有返回true,没有返回false
```
var arr10 = [1,5,7,8,9,]
var arr11 = arr10.includes(5)
var arr12 = arr10.includes(4)
console.log(arr11)//true
console.log(arr12)//false
```
- 空位是指数组的某一个位置没有值，空位(没有值)不等于undefined(有值)
7. 数组的推导
```
var arr13 = [2,3,4,5]
var arr14 = [for(i of arr13) i *2]
console.log(arr14)//4,6,8,10
var arr15 = [2,3,4,5]
var arr16 = arr15.map(() => i * 2)
console.log(arr16)//4,6,8,10
```
### 函数的扩展
1. 函数的参数设置默认值，可以直接写在参数定义的后面
```
function arr(x,y='b'){
    console.log(x,y)
}
arr(a)
//a,b
```
2. rest搭配的是数组参数
function add(...values){
    let sum =0;
    for(var i of values){
        sum += i
    },
    return sum;
}
add(1,2,3)//5
3. ...扩展运算符将一个数组用逗号分隔的参数
