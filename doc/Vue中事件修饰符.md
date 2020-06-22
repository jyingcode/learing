1. .once

```
<div v-on:click.once = "spread"></div>
```

-   点击事件只会触发一次。

2. .prevent

```
<div v-on:submit.prevent = "spread"></div>
```

-   某些标签拥有自身的默认事件，如 a[href="#"]，button[type="submit"] 这种标签在冒泡结束后会开始执行默认事件,提交事件不再重新加载页面。

3. .stop

```
<div v-on:click.stop = "spread"></div>
```

-   阻止单击事件继续传播。

4. .capture

```
<div v-on:click.capture = "spread"></div>
```

-   添加事件监听器时使用事件捕获模式，即内部元素触发的事件先在此处理，然后才交给内部元素处理。

5. .self

```
<div v-on:click.self = "spread"></div>
```

-   只有当在 even.target 时当前元素自身时触发处理函数，即事件不是从内部触发的。

6. passive

```
<div v-on:click.passive = "spread"></div>
```

-   滚动事件的默认行为（即滚动行为）就会立即执行。
