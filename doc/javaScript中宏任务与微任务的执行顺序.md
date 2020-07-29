#### 宏任务：

-   是指消息队列中的等待被主线程执行的事件，宏任务执行时都会重新创建栈，然后调用宏任务中到函数，栈也会随着变化，但宏任务执行结束时，栈也会随之销毁。

-   包括整体代码 script，setTimeout，setInterval，new Promise

#### 微任务：

-   可以把微任务看成是一个需要异步执行的函数，执行时机是在主函数执行结束之后、当前宏任务结束之前

-   Promise.then，process.nextTick(node 中)。

*   微任务是基于消息队列、事件循环、UI 主线程还有堆栈而来的

```
setTimeout(function(){
    console.log('1')
});
new Promise(function(resolve){
    console.log('2');
    resolve();
}).then(function(){
    console.log('3')
});
console.log('4');
new Promise(function(resolve){
    console.log('5');
    resolve();
}).then(function(){
    console.log('6')
});
setTimeout(function(){
    console.log('7')
});
function bar(){
    console.log('8')
    foo()
}
function foo(){
    console.log('9')
}
console.log('10')
bar()
```

### 解析

1. 首先浏览器执行 Js 代码由上至下顺序，遇到 setTimeout，把 setTimeout 分发到宏任务 Event Queue 中
2. new Promise 属于主线程任务直接执行打印 2
3. Promis 下到 then 方法属于微任务，把 then 分到微任务 Event Queue 中
4. console.log('4')属于主线程任务，直接执行打印 4
5. 又遇到 new Promise 也是直接执行打印 5，Promise 下到 then 分发到微任务 Event Queue 中
6. 又遇到 setTimouse 也是直接分发到宏任务 Event Queue 中，等待执行
7. console.log('10')属于主线程任务直接执行
8. 遇到 bar()函数调用，执行构造函数内到代码，打印 8，在 bar 函数中调用 foo 函数，执行 foo 函数到中代码，打印 9
9. 主线程中任务执行完后，就要执行分发到微任务 Event Queue 中代码，实行先进先出，所以依次打印 3，6
10. 微任务 Event Queue 中代码执行完，就执行宏任务 Event Queue 中代码，也是先进先出，依次打印 1，7。

-   最终结果：2，4，5，10，8，9，3，6，1，7

### 总结

-   我们可以清晰地看出，主线程处于微任务之前执行，微任务是处于宏任务之前执行。
