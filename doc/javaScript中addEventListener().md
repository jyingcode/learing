
#### addEventListener() 方法用于向指定元素添加事件

<div  id="test">测试</div>
```
document.querySelector('#test').addEventListener('click',()=>{
console.log('test click')
},false)
```

##### document.addEventListener(event, function, useCapture)

##### 第一个参数参数event
1. 必须。字符串，指定事件名。
2. 注意: ﻿
﻿不要使用 "on" 前缀。 例如，使用 "click" ,而不是使用 "onclick"。﻿


##### 第二个参数function
1. 必须。指定要事件触发时执行的函数。
2. 当事件对象会作为第一个参数传入函数。 事件对象的类型取决于特定的事件。
3. 例如， "click" 事件属于 MouseEvent(鼠标事件) 对象。


##### 第三个参数useCapture
1. 布尔值，指定事件是否在捕获或冒泡阶段执行。
2. 
true - 事件句柄在捕获阶段执行
false- false- 默认。事件句柄在冒泡阶段执行