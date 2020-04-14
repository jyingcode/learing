### JavaScript对象
1. 宿组对象：由 JavaScript 宿主环境提供的对象，它们的行为完全由宿主环境决定。
* ducument history navigator location*
2. 内置对象：由Javascript语言提供的对象
- 固有对象：由标准规定，随着 JavaScript 运行时创建而自动创建的对象实例。
- 原生对象：可以由用户通过 Array、RegExp 等内置构造器或者特殊语法创建的对象。
- 普通对象：由{}语法、Object 构造器或者 class 关键字定义类创建的对象，它能够被原型继承。
### css语法和@选择器
1. @charset
- 用于提示 CSS 文件使用的字符编码方式，它如果被使用，必须出现在最前面
2. @import
- 用于引入一个 CSS 文件
3. @media
- 能够对设备的类型进行一些判断
4. @page
- 用于分页媒体访问网页时的表现设置，页面是一种特殊的盒模型结构，除了页面本身，还可以设置它周围的盒。
5. @ counter-style
- 产生一种数据，用于定义列表项的表现
6. @ key-frames
- 产生一种数据，用于定义动画关键帧
7. @ fontface
- 用于定义一种字体，icon font 技术就是利用这个特性来实现的
8. @ support
- 检查环境的特性，它与 media 比较类似
9. @ namespace
- 用于跟 XML 命名空间配合的一个规则，表示内部的 CSS 选择器全都带上特定命名空间
10. @ viewport
- 用于设置视口的一些特性，不过兼容性目前不是很好，多数时候被 HTML 的 meta 代替

### css伪元素
1. 优先级
- 无连接符号>有链接符号 同一优先级履行“后面覆盖前面原则”
``` 
    div id="my" class="x y">text
    .x { 
        background-color:lightblue;
    }
    .y { 
        background-color:lightgreen;
    }
```
- 优先级是针对单条规则的
```
<div id="my" class="x y z">text<div>
.x { 
    background-color:lightblue;
    }
.z { 
    background-color:lightblue;
    }
.y { 
    background-color:lightgreen;
    }
```
### 兼容性达到可用的伪元素有以下几种
1. first-line
- 表示元素的第一行
```
<p>
This is a。 
somewhat。 
</p>
p::first-line { 
    text-transform: uppercase；
    }
```
2. first-letter
- 表示元素元素的第一个字母
```
<p> 
somewhat。 
</p>
p::first-letter { 
    text-transform: uppercase; font-size:2em; float:left; 
    }
```
3. before
- 表示在元素内容之前插入一个虚拟的元素
```
<p class="special">I'm element</p>
p.special::before { 
    display: block; 
    content: "pseudo! ";
    }
```
4. after
- 则表示在元素内容之后插入