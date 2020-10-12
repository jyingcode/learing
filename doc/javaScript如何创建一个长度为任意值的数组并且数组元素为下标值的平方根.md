#### 用到技术有：Array.from() new Array() Array.map() Array.forEach()
##### Array.from()
- Array.from() 称为类数组对象：所谓类数组对象，最基本的要求就是具有length属性的对象。就是将一个类数组对象或者可遍历对象转换成一个真正的数组。
- new Array() 实例的创建,如果知道数组的长度，这里假设数组长度为30，那么就可以这样写 new Array(30)
- Array.map() 方法返回一个新数组，数组中的元素为原始数组元素调用函数处理后的值。按照原始数组元素顺序依次处理元素。
- Array.forEach() 用于调用数组的每个元素，并将元素传递给回调函数。对于空数组是不会执行回调函数的。
###### Array.map()方法的代码实现
```
var arr = Array.from(new Array(30));
var arr1 = arr.map((item, index) => index * 2)
console.log(arr1)

(30) [0, 2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24, 26, 28, 30, 32, 34, 36, 38, 40, 42, 44, 46, 48, 50, 52, 54, 56, 58]
```
###### Array.forEach()方法代码实现
```
var arr = Array.from(new Array(30))
arr.forEach((item, index, arr2) => {
    arr[index] = index * 2
})
console.log(arr)
(30) [0, 2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24, 26, 28, 30, 32, 34, 36, 38, 40, 42, 44, 46, 48, 50, 52, 54, 56, 58]
```