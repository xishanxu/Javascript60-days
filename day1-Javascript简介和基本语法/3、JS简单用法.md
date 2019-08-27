## 1、JavaScript语法

#### 	1️⃣区分大小写， js的一切都区分大小写 变量名 test 和 Test是两个不同的变量

#### 	2️⃣标识符 ，（指的是变量、函数、属性的名字或者函数的参数），按照以下规则来组合的字符：

​			I、第一个字符必须是字母、下划线（ _ ）或者一个美元符号（ $ ）

​			II、其他的字符可以是字母、下划线、美元符号 或者 数字

​			III、标识符中的字母也可以包含ASCII或者Unicode字母字符，但是不推荐这么做

#### 	3️⃣注释： 注释是不被执行的代码

```javascript
// 单行注释

多行注释以/*开头  以*/结尾
/*
*	 这是一个多行注释
*	（块级注释）
*/
```



#### 	4️⃣严格模式 ES5增加的   script标签中写入 "use strict" 进入严格模式，用得比较少

#### 	5️⃣js中语句以分号结尾，如果省略了分号，则由解析器自动确定语句的结尾

#### 	6️⃣多条的语句要组合在一个代码块当中，代码块以 ( { ) 开头，以 ( } ) 结尾 ； 这是C语言的代码风格

```javascript
if (test) {
	test = false;
	alert(test);
}
```

#### 	7️⃣关键字和保留字  （不能用作标识符）

![](https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1567485019&di=cb2bfbdbbc152475f52e1768634df68c&imgtype=jpg&er=1&src=http%3A%2F%2Fimage.bubuko.com%2Finfo%2F201801%2F20180115212414416857.png)

## 2、向页面输出内容	

```javascript
document.write("hello world");

document.write("<strong>我很man</strong>");

// 转义字符: &lt; || &gt;

document.write("&lt;strong&gt;我很man&lt;/strong&gt;");
```

## 3、变量

	### 	每一个变量就仅仅是一个用来保存值的占位符而已，JavaScript的变量是松散类型的，所谓松散类型就是可以用来保存任何类型的数据。 定义变量要用 var 操作符（注意var是一个关键字）后跟一个变量的名字；下面我举个栗子：

```javascript
var result;
// 这行代码我定义了一个名为result的变量，该变量可以用来储存任何值（像这样没有经过初始化的变量，会保存一个特殊的值undefined），JavaScript也支持直接初始化一个变量，如下代码：
var message = 10086;
// 这里变量message保存了一个数字10086

// 修改变量:
var test = 'hi';
test = 10086;
```

## 4、变量的类型 (数据类型)

### 	1️⃣基本数据类型(简单数据类型): 一共有7种基本数据类型

​		undefined 

​		