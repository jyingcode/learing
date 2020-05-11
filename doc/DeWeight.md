### 数组的去重方法
1. ES6 Set
```
function Arr(arr){
    return Array.from(new Set(arr))
}
var arr = [1,1,2,2,3,4,5,5,6,6,7,8,8,7] 
console.log(Arr(arr))
*[1,2,3,4,5,6,7,8]*
```
2. indexof
```
function Arr(arr){
    if(!Array.isArray(arr)){
        console.log('type error!')
        return
    }
    var bar = []
    for(var i = 0;i < arr.length;i++){
        if(bar.indexOf(arr[i])===-1){
            bar.push(arr[i])
        }
    }
    return bar;
}
var arr = [1,1,36,36,23,23,45,45] 
console.log(Arr(arr))
* [1,36,23,45]*
```
3. filter
```
function Arr(arr){
    return arr.filter(function(item,index,arr){
        return arr.indexOf(item,0)===index
    })
}
var arr = [11,22,33,22,11,33,88,88,44,44]
console.log(Arr(arr))
* [11,22,33,88,44]*
```
4. for
```
function Arr(arr){
    for(var i = 0;i <arr.length;i++){
        for(var j=i+1;j < arr.length;j++){
            if(arr[i]==arr[j]){
                arr.splice(j,1)
                j--;
            }
        }
    }
    return arr
}
var arr = [12,13,12,13,14,14,15,16,15,16]
console.log(Arr(arr))
* [12,13,14,15,16]*
```