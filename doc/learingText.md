### JavaScript 中的函数

-   既可以被调用，还可以作为变量、参数和返回值

1. 调用

```
function foo(){
    var test = 1
    console.log(test)
}
foo()
```

2. 作为变量，变量和返回值

```
function foo(){
    var number = 1
    function bar(){
        number++
        console.log(number)
        } return bar
    }
    var mybar = foo()
    mybar()
```

### JavaScript 的函数特点

1. 继承

-   只是在对象中添加了一个称为原型的属性，把继承的对象通过原型链接起来，就实现了继承，我们把这种继承方式称为基于原型链继承

2. 封装

-

3. 多态

-

### 对象的值有哪些类型

1. 原始类型

-   指值本身无法被改变

```
 firstname= "Javascript "
```

2. 对象类型

-   对象的属性值也可以是另外一个对象

```
var info = {
    age: "26"
    color: " red"
}
```

3. 函数类型

-   如果对象中的属性值是函数,这种函数叫方法

```
info.firstname = function(){
   console.log()
}
```

### 如何实现对象继承

1. 利用 **proto** 实现继承

```
var animal = {
    type: "Default",
    getInfo: function () {
        return ${this.type}，
    }
}
var dog = {
        type: "Dog",
    }
dog.__proto__ = animal
dog.getInfo()

//call与apply的区别//
const text = {
    Msg:() =>{
    }
}
function Add(name,age) {
      console.log(name,age)
}
Add.call(text,'wanger',30)
Add.apply(text,['wanger',26])
```

2. 创建构造函数

```
function DogFactory(type,color){
    this.type = type
    this.color = color
}
var dog =new DogFactory('Dog','Black')
```

### 怎样查找变量

```
var name = '极客时间'
var type = 'global'
function foo(){
    var name = 'foo'
    console.log(name)
    console.log(type)
    }
    function bar(){
        var name = 'bar'
        var type = 'function'
    foo()
    }
bar()
```

-   打印结果为“foo”和“global”

### 函数作用域和全局作用域

-   当函数需要使用某个变量或者调用某个函数时，便会优先在该函数作用域中查找相关内容，依次向上找，直到找到为止。

1. 全局作用域

-   启动浏览器过程中就创建了，且一直保存在内存中不会被销毁的，直至浏览器退出

2. 函数作用域

-   函数作用域是在执行该函数时创建的，当函数执行结束之后，函数作用域就随之被销毁掉了。

### 函数表达式

1. 函数声明

```
var foo(){
    console.log()
}
```

2. 函数表达式

```
var foo = function(){
    console.log()
}
```

-   遇到普通的变量声明，会将其提升到作用域中，并给该变量赋值为 undefined，如果遇到的是函数声明，会在内存中声明生成函数对象，并将该对象提升到作用域中。\*

### 函数表达式和函数声明到区别

1. 函数表达式是在表达式语句中使用 function 的，最典型的表达式是“a=b”这种形式，因为函数也是一个对象，我们把“a = function (){}”这种方式称为函数表达式；
2. 在函数表达式中，可以省略函数名称，从而创建匿名函数
3. 一个函数表达式可以被用作一个即时调用的函数表达式
4. 立即调用函数表达式

```
function(){

}（）
```
