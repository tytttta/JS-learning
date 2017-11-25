# js基本语法（下）

## 1.1 js语句
### 1.1.1 if/els语句
````
if(condition1)
{
 code;
}
else if(condition2)
 {
 code;
 }
else{
code;
}
````

### 1.1.2 switch/case语句
````
switch(x)
{
case x1:
  code block;
  break;
case x2;
  code block;
  break;
default"
  code block;
}
````
### 1.1.3for 循环
````
for(变量=初始值；循环条件；变量累加）
{
  code block;
}
````

### 1.1.4 while 循环
````
while(condition)
{
  code;
}
````
do/while循环：
````
do {
 code block;
 }while(ondition);
````

### 1.1.5 break和continue语句
-- break语句在循环体中表示立刻跳出循环

-- continue语句表示停止本次循环，执行下一次循环

## 1.2 js函数
JavaScript 的函数可以封装那些在程序中可能要多次用到的模块，并可作为 事件驱动 的结果而调用的程序，从而实现一个函数把它与事件驱动相关联，
这是与其它语言不同的地方。

在js中，函数使用关键词function定义，函数可以有多个参数，格式为：
````
function 函数名（参数1， 参数2）
{
  函数体；
  return 返回值；
}
````

**函数的重复声明：如果多次采用 function 命令重复声明同一个函数，则后面的声明会覆盖前面的声明**
