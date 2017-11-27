# js简介

## 1.1 js是什么
JavaScript 是一种脚本语言，它的解释器被称为 JavaScript 引擎。JavaScript 被发明用于在 HTML 网页上使用，给HTML网页增加动态功能。

### 案例：
HTML文件：
````
<html>
<head></head>
<body>

<script>
alert("hello world!");
</script>

</body>
</html>
````
JavaScript 代码放在 <script>……</script> 标签里，这段代码的效果是，弹出一个小框，显示“hello world!”。

## 1.2 js 放哪里
1. 放在<body></body>中

2. 放在<head></head>中

3. 放在单独的js文件中 <script src="XX.js"></script>

**执行顺序按照<script>脚本的顺序执行**
