### 什么是函数作用域和全局作用域
- 在执行阶段，执行一个函数时，当该函数需要使用某个变量或者调用了某个函数时，便会优先在该函数作用域中查找相关内容。
- 全局作用域是指某个变量会被window对象属性保存
### 函数作用域和全局作用域的区别
- 全局作用域是在浏览器启动过程中就创建了，且一直保存在内存中不会被销毁的，直至浏览器退出。 
- 而函数作用域是在执行该函数时创建的，当函数执行结束之后，函数作用域就随之被销毁掉了。
 ```
 var name = "zhangsan"
 var age = "20"
 function foo(){
     var name = "lisi"
     console.log(name)
     
 }
 function bar(){
     var name = "wanger"
     foo()
     console.log(age)
 }
 bar()
 console.log(name)
 ```
 * lisi,20,30*
 1. 这里代码有三个作用域。分别是全局作用域，foo()函数作用域和bar()函数作用域，
 2. 变量作用域的查找都是按照当前函数作用域–> 全局作用域这个路径来的。
 3. foo()函数里面的name = "lisi",所以console.log(name)指向的是foo()函数的“name”
 4. bar()函数里的console.log(age)则是指向window下的var age = "20",
 5. window下的console.log(name)则指向window下var name ="zhangsan"
 - 作用域就是用来存放变量和函数的地方，全局作用域中存放了全局环境中声明的变量和函数，函数作用域中存放了函数中声明的变量和函数。
 - 当在某个函数中使用某个变量时，会去这些作用域中查找相关变量。沿着这些作用域查找的路径，我们就称为作用域链。
 ### 闭包与自执行函数
 ```
 function outer(){
     var result = new Array()
     for(var i = 0;i < 2;i++){
         result[i] = function(){
             return:i
         }
     }
     return result
 }
 var fn = outer()
 console.log(fn[0]())
 console.log(fn[1]())
 ```
 ```
 function outer1(){
     var result = new Array()
     for(let i = 0;i < 2;i++){
         result[i] = function(){
             return:i
         }
     }
     return result
 }
 var fn1 = outer1()
 console.log(fn1[0]())
 console.log(fn1[1]())
 ```
 ```
 function outer2(){
     var result = new Array()
     for(var i = 0;i < 2;i++){
        result[i] =(function(a){
            return a
         })(i)
     }
     return result
 }
 var fn2 = outer2()
 console.log(fn2[0])
 console.log(fn2[1])
 ```
 * 依次打印结果为[2,2],[0,1],[0,1]*
 ### var与let区别
 ```
 function outer(){
     var result = new Array()
     for(var i = 0;i < 2;i++){
         result[i] = function(){
             return:i
         }
     }
     return result
 }
 var fn = outer()
 console.log(fn[0]())
 console.log(fn[1]())
 ```
 ```
 function outer1(){
     var result = new Array()
     for(let i = 0;i < 2;i++){
         result[i] = function(){
             return:i
         }
     }
     return result
 }
 var fn1 = outer1()
 console.log(fn1[0]())
 console.log(fn1[1]())
 ```
 - (let i = 0;i < 0;i++) i虽然在全局作用域声明，但是在for循环体局部作用域中使用的时候，变量会被固定，不受外界干扰。i变量只在花括号内有效,i 是循环体内局部作用域，不受外界影响.let不允许在相同作用域内，重复声明同一个变量
### 自执行函数
```
(function(sum){
  console.log(sum)
})()
```

