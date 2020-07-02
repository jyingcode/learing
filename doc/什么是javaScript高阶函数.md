1. 高阶函数是对其他函数进行操作的函数，可以将它们作为参数或返回它们。简单来说，高阶函数是一个函数，它接收函数作为参数或将函数作为输出返回。

```
var arr =[1,2,3,4,5]
var arr1 = []
for(let i = 0;i < arr.length;i++){
    arr1.push(arr[i] * 3)
}
console.log(arr1) //[3,6,9,12,15]
//高阶函数
const arr2 = arr.map(function(item,index,arr){
    return item * 3
})
console.log(arr2) //[3,6,9,12,15]

```

```
var persons = [
  { 'name': 'zhangsan', age: 22 },
  { 'name': 'lisi', age: 28 },
  { 'name': 'wanger', age: 19 },
  { 'name': 'mazi', age: 31 },
]
let Age = persons.filter(item => item.age > 21);
console.log(Age);
```

#### 高阶函数的意义

1. 函数可以作为参数

```
function bar(fn){
    if(typeof fn === "function"){
        fn()
    }
}
bar(function () {})//调用
```

2. 函数可以作为返回值

```
function bar(){
    return function (){}
}
const fn = bar ()//调用
console.log(fn)
```

-   高阶函数是对基本算法的再度抽象，可以利用这一点提高代码的抽象度，实现最大限度的代码重构，\*
