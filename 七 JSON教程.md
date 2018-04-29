# 1 JSON教程
JSON：JavaScript Object Notation(JavaScript 对象表示法)。

- json是存储和交换文本信息的语法，类似XML。json比XML更小，更快，更容易解析。

- JSON 独立于语言：JSON 使用 Javascript语法来描述数据对象，但是 JSON 仍然独立于语言和平台。JSON 解析器和 JSON 库支持许多不同的编程语言。 
目前非常多的动态（PHP，JSP，.NET）编程语言都支持JSON。

- JSON 具有自我描述性，更易理解。

- JSON 文本格式在语法上与创建 JavaScript 对象的代码相同。
由于这种相似性，无需解析器，JavaScript 程序能够使用内建的 eval() 函数，用 JSON 数据来生成原生的 JavaScript 对象。


JSON 实例：
````
{
"sites": [
{ "name":"菜鸟教程" , "url":"www.runoob.com" }, 
{ "name":"google" , "url":"www.google.com" }, 
{ "name":"微博" , "url":"www.weibo.com" }
]
}
````

# 2 JSON 简介

## 2.1 与 XML 相同之处
- JSON 是纯文本
- JSON 具有"自我描述性"（人类可读）
- JSON 具有层级结构（值中存在值）
- JSON 可通过 JavaScript 进行解析
- JSON 数据可使用 AJAX 进行传输

## 2.2 与 XML 不同之处
- 没有结束标签
- 更短
- 读写的速度更快
- 能够使用内建的 JavaScript eval() 方法进行解析
- 使用数组
- 不使用保留

## 2.3 为什么使用 JSON？
对于 AJAX 应用程序来说，JSON 比 XML 更快更易使用：

**使用 XML**

读取 XML 文档：

使用 XML DOM 来循环遍历文档

读取值并存储在变量中

**使用 JSON**

读取 JSON 字符串：

用 eval() 处理 JSON 字符串

# 3 JSON语法
JSON 语法是 JavaScript 对象表示语法的子集。

- 数据在名称/值对中
- 数据由逗号分隔
- 大括号保存对象
- 中括号保存数组

## 3.1 JSON 名称/值对
JSON 数据的书写格式是：名称/值对。

名称/值对包括字段名称（在双引号中），后面写一个冒号，然后是值：
````
"name" : "菜鸟教程"
````
这很容易理解，等价于这条 JavaScript 语句：
````
name = "菜鸟教程"
````

## 3.2 JSON 值
JSON 值可以是：

- 数字（整数或浮点数）
- 字符串（在双引号中）
- 逻辑值（true 或 false）
- 数组（在中括号中）
- 对象（在大括号中）
- null

## 3.3 JSON 数字
JSON 数字可以是整型或者浮点型：
````
{ "age":30 }
````

## 3.4 JSON 对象
JSON 对象在大括号（{}）中书写：

对象可以包含多个名称/值对：
````
{ "name":"菜鸟教程" , "url":"www.runoob.com" }
````
这一点也容易理解，与这条 JavaScript 语句等价：
````
name = "菜鸟教程"
url = "www.runoob.com"
````

## 3.5 JSON 数组
JSON 数组在中括号中书写：

数组可包含多个对象：
````
{
"sites": [
{ "name":"菜鸟教程" , "url":"www.runoob.com" }, 
{ "name":"google" , "url":"www.google.com" }, 
{ "name":"微博" , "url":"www.weibo.com" }
]
}
````
在上面的例子中，对象 "sites" 是包含三个对象的数组。每个对象代表一条关于某个网站（name、url）的记录。

## 3.6 JSON 使用 JavaScript 语法
因为 JSON 使用 JavaScript 语法，所以无需额外的软件就能处理 JavaScript 中的 JSON。

通过 JavaScript，您可以创建一个对象数组，并像这样进行赋值：

实例:
````
var sites = [
    { "name":"runoob" , "url":"www.runoob.com" }, 
    { "name":"google" , "url":"www.google.com" }, 
    { "name":"微博" , "url":"www.weibo.com" }
];
````
可以像这样访问 JavaScript 对象数组中的第一项（索引从 0 开始）：
````
sites[0].name;
````
返回的内容是：
````
runoob
````

可以像这样修改数据：
````
sites[0].name="菜鸟教程";
````
## 3.7 JSON 文件
JSON 文件的文件类型是 ".json"
JSON 文本的 MIME 类型是 "application/json"

# JSON对象
## 对象语法
实例
````
{ "name":"runoob", "alexa":10000, "site":null }
````
JSON 对象使用在大括号{}中书写。

对象可以包含多个 key/value（键/值）对。

key 必须是字符串，value 可以是合法的 JSON 数据类型（字符串, 数字, 对象, 数组, 布尔值或 null）。

key 和 value 中使用冒号(:)分割。

每个 key/value 对使用逗号(,)分割。

## 访问对象值
你可以使用点号（.）来访问对象的值：

实例
````
var myObj, x;
myObj = { "name":"runoob", "alexa":10000, "site":null };
x = myObj.name;
````
你也可以使用中括号（[]）来访问对象的值：

实例:
````
var myObj, x;
myObj = { "name":"runoob", "alexa":10000, "site":null };
x = myObj["name"];
````
