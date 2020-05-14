1. 怎么用apply实现call方法
```
Function.prototype.maCall = function(...arg) {
    const content = arg.splice(0,1)
    this.apply(content,[...arg])
}
function test (a,b){
    console.log(a+b)
}
test.maCall(null,10,20)
```
2. 封装map函数
- 手动封装
```
var arr = [1,2,3,4,5]
Array.prototype.myMap = function(fn){
    let result = []
    for(let i = 0; i < this.length; i++){
        result.push(fn.apply(this,[arr[i]]))
    }
    return result
}
var newArr = arr.myMap((e) => {
    return e * 2
})
console.log(newArr)
*[2,4,6,8,10]*
```
- 直接使用
```
var arr = [1,2,3,4,5]
var result = arr.map(e => e * 2)
console.log(result)
*[2,4,6,8,10]*
```
3. 封装forEach
- 手动封装
```
var arr = [1,2,3]
Array.prototype.myForEach = function(fn){
    for(let i = 0; i < this.length;i++){
          fn.call(this,this[i],i,this)
    }
}
arr.myForEach(function(v,i,arr){
   console.log(v)
})
*1,2,3*
```
- 直接使用
```
var arr = [1,2,3]
arr.forEach(function(e){
   console.log(e)
})
*1,2,3*
```
4. 封装fliter
- 手动封装
```
var arr = [1,3,,5,7,9]
Array.prototype.myFilter = function(fn, context){
    var result = []
    for(let i = 0;i < this.length;i++){
       var res = fn.call(this,this[i],i,this)
      if(res){
           result.push(this[i])
      }
    }
    return result
}
var newArr = arr.myFilter(function(v){
   return v >= 5
})
console.log(newArr)
*[5,7,9]*
```
- 直接使用
```
var nums = [1,3,5,7,9];
var res = nums.filter((num) => {
  return num > 5;
});
console.log(res); 
*[7,9]*
```

