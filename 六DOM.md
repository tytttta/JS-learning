# JS-DOM
本章主要介绍js的dom操作，内容包括：
- 通过ID、名字、标签名选取元素
- 通过getAttribute和setAttribute获取和设置元素属性
- 通过parentNode获取父元素、createElement动态地创建节点、appendChild和removeChild动态地添加或删除节点

## 1.1 基本概念
### 1.1.1 什么是DOM
DOM是**文档对象模型**（Document Object Model）的简称，它的基本思想是把结构化文档（如HTML和XML）解析成一系列节点，再由这些节点组成一个
树状结构（DOM Tree）。所有节点和最终的树状结构，都有规范的对外接口，以达到使用编程语言操作文档的目的。所以DOM可以理解为文档的编程接口。

DOM不属于js，但是操作DOM是js最常见的任务，而js也是常用于DOM操作的语言。

### 1.1.2 节点
DOM最小的组成单位叫做节点（node），一个文档的树形结构（DOM树），就是由各种不同类型的节点组成。

对于HTML文档，节点主要有以下几种类型：

|节点|名称|含义|
|----|----|----|
|Document|文档节点|整个文档（window.document）|
|DocumentType|文档类型节点|文档的类型|
|Element|元素节点|HTML元素|
|Attribute|属性节点|HTML元素的属性（如class=“right”）|
|Text|文本节点|HTML文档中出现的文本|
|DocumentFragment|文档碎片节点|文档中的片段|

## 1.2选取文档元素

### 1.2.1通过ID选取元素
可以通过使用方法getElementById()通过元素ID选取元素。如：
````
<html>
<body>
<div id="my_div"></div>

<script>
    document.getElementById("my_div").style.height="100px";  // 设置 my_div 高度为 100px
    document.getElementById("my_div").style.background="red"; // 设置 my_div 颜色为 红色
</script>

</body>
</html>
````
通过getElementById()设置了id为my_div的div标签的高度和颜色。

### 1.2.2 通过名字（Name）或标签名（TagName）选取元素
除了通过ID选取元素，还可以使用**getElementsByName**方法或**getElementsByTagName**方法找到元素，如果有多个同类型标签，需要使用下标来确认。
**(注意有s）**
````
<html>
<body>
<input type="text" />
<input type="text" />

<script>
document.getElementsByTagName("input")[0].value="hello";   // 下标为 [0] 表示选取第 1 个 input 标签
document.getElementsByTagName("input")[1].value="shiyanlou"; // 下标为 [1] 表示选取第 2 个 input 标签
</script>

</body>
</html>
````

## 1.3 节点、属性操作和文档遍历
### 1.3.1 查询和设置元素的属性
可以通过getAttribute和setAttribute查询和设置元素的属性。
````
<html>
<head>
<style>
.class_1 {
    height:100px;
    width:100px;
    background:red;
}
.class_2 {
    height:100px;
    width:100px;
    background:blue;
}
</style>
</head>

<body>
<div id="div_1" class="class_1"></div>
<br/>
<a>before:</a>

<script>
document.write(document.getElementById("div_1").getAttribute("class")); // 查询 div_1 的属性
</script>

<br/>
<a>after:</a>

<script>
document.getElementById("div_1").setAttribute("class","class_2");  // 修改 div_1 的属性为 class_2
document.write(document.getElementById("div_1").getAttribute("class")); // 再次查询 div_1 的属性
</script>

</body>
</html>
````
代码可见，一开始 div_1 的属性为 class_1，我们通过getAttribute() 方法可以查看到该结果；

然后我们使用 setAttribute() 方法将 div_1 的属性设置为 class_2 ，然后再次使用 getAttribute() 方法查询，可见属性已经变为 class_2 .

### 1.3.2 父节点
通过parentNode()方法可以查看并操作一个节点的父节点，案例：找到id为demo的元素的父节点，并输出其class的名称：
````
<html>
<body>
<div class="demo-parent">
    <div id="demo">        
    </div>
</div>

<script>
    document.write(document.getElementById("demo").parentNode.getAttribute("class"));
</script>
</body>
</html>
````

### 1.3.3 创建和插入节点
js可以动态的在界面中创建并插入节点，需要用到createElement()、appendChild()方法，他们的作用分别是创建、插入节点。

案例：创建一个div并设置高度为100px，背景颜色为red，并追加到body后面。
````
<html>
<body>
<div style="background:#00F; height:100px"></div>
<script>
    var mydiv = document.createElement("div");
    mydiv.style.height = "100px";
    mydiv.style.background = "red";
    document.getElementsByTagName("body")[0].appendChild(mydiv);
</script>
</body>
</html>
````

### 1.3.4 删除节点
通过removeChild（）方法：
````
html>
<head>
</head>
<body>
<div>
    <div id="div_red" style="background:#F00; height:100px"></div>
    <div id="div_blue" style="background:#00F; height:100px"></div>
</div>
<script>
function remove_red(){
    var obj = document.getElementById("div_red");
    obj.parentNode.removeChild(obj);
    }
</script>
<button onclick="remove_red()">remove red div</button>
</body>
</html>
````

## 2 作业

在一个页面内实现：

通过按钮改变页面颜色，通过按钮创建和插入节点等本节实验中的功能。

````
<html>
<head>
<script>
function color(){
	document.getElementById("div").style.background="blue";
}

function add(){
	var div2=document.createElement("div");//此处参数应为HTML中的元素名
	div2.style.height="200px";
	div2.style.background="yellow";
	document.getElementsByTagName("body")[0].appendChild(div2);
}
function remove(){
	var node=document.getElementById("div");
//	document.write(document.getElementsByTagName("div")[2].getAttribute("id")); 测试：获取新建节点的id
	node.parentNode.removeChild(node);
}

</script>
</head>
<body>
<div id="div" style="background:red; height:100px"></div>
<div id="div3">
<button id="bt1" onclick="color()">color</button>
<button id="bt2" onclick="add()">add</button>
<button id="bt3" onclick="remove()">remove </button>
</div>
</body>
</html>
````

