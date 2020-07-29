#### toString()
1. 数组
```
var arr = [1,2,3,4]
arr.toString()
// "1,2,3,4"
```
2. 对象
```
var obj = {}
obj.tostring()
// "[object,object]"
```
3. 函数
```
var fn = function () {}
fn.toString()
//"function () {}"
```
4. 字符串 
```
var str = ""
str.toString()
//""
```
- 负责处理非字符串到字符串的强制转换，将对象强制类型转换为string是通过ToPrimitive抽象操作完成的。
#### valueOf()
1. 数组
```
var arr = [1,2,3,4]
arr.valueOf()
// [1,2,3,4]
```
2. 对象
```
var obj = {}
obj.valueOf()
//{}
```
3. 函数
```
var fn = function () {}
fn.valueOf()
//fn () {}
```
4. 字符串 
```
var str = ""
str.valueOf()
//""
```
- 返回数据本身数据类型
#### 隐式强制转换
```
[] + [] == "" //true
{} + [] == 0  //true
{} + {}
"[object Object][object Object]"
fn() + fn()
"function () {
                return name
            }function () {
                return name
            }"
'' + '' == '' //true
```
```
const obj1 = {}
const obj2 = {
    toString() {
        return 3
    },
    valueOf() {
         return 4
    }
}
const arr = [1, 2, 3, 4]
console.log(obj1 + arr)
//[object Object]1,2,3,4
```
```
const obj1 = {
    toString() {
        return 1
    },
     valueOf() {
        return {}
    }
}
const obj2 = {
    toString() {
        return 3
    },
    valueOf() {
        return 4
    }
}
const arr = [1, 2, 3, 4]
console.log(obj1 + arr)
//11,2,3,4
```
