1. 命令式编程

```
var arr = [1, 2, 3, 4]
var newArr = (arr) => {
	const res = []
	for (let i = 0; i < arr.length; i++) {
		res.push(arr[i] + 1)
	}
	return res
}
console.log(newArr(arr)) //[2,3,4,5]
```

-   命令式编程，详细的命令机器去处理事情来达到想要得到的结果，这段代码是”死“的，代码是不可复用，如果增加需求或者改变需求 arr[i]加 3，就要重新定义一个函数

```
var arr = [1, 2, 3, 4]
var newArr = (arr) => {
	const res = []
	for (let i = 0; i < arr.length; i++) {
		res.push(arr[i] + 1)
	}
	return res
}
console.log(newArr(arr)) //[4,5,6,7]
```

这样就会存在过多的函数，占用内存大导致内存溢出。

1. 函数式编程

```
var arr = [1, 2, 3, 4]
var newArr = (arr, fn) => {
	const res = []
	for (let i = 0; i < arr.length; i++) {
		res.push(fn(arr[i]))
	}
	return res
}
const add = (item) => item + 1
const sum = newArr(arr, add)
console.log(sum)  //[2,3,4,5]
```

-   通过函数式编程也可以实现上面的需求.
    如果需求改成和上面一样增加或者改变 arr[i]加 3，就不用重新定义一个函数了,可以这样

```
var arr = [1, 2, 3, 4]
var newArr = (arr, fn) => {
	const res = []
	for (let i = 0; i < arr.length; i++) {
		res.push(fn(arr[i]))
	}
	return res
}
const add = (item) => item + 1
const sum = newArr(arr, add)
console.log(sum)  //[2,3,4,5]
const newNeeds = (item) => item + 3
const result = newArr(arr, newNeeds)
console.log(result) //[4,5,6,7]
```

###### 函数式编程又分为纯函数和非纯函数

1. 纯函数

-   如果函数的调用参数相同，就永远返回相同的结果，它不依赖于程序执行期间函数外部任何状态或数据的变化，只依赖于它传入的参数。即相同的输入，永远得到相同的输出。而且没有副作用，这样可以保证代码的《稳定性》和《可靠性》

2. 非纯函数

-   会改变自己的输入值
