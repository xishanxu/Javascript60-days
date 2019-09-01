# 1、JavaScript预编译与执行顺序

	## 	在说预编译和执行顺序之前，我们先回顾一下昨天说的变量作用域，以及补充一些概念：

	### 	昨天说了，作用域就是，内层环境可以访问外层中的变量和函数，而外层环境不能访问内层的变量和函数

```javascript
局部作用域 可以访问 外层作用域的变量 如下：
var scope = 'global';
fucntion checkScope() {
	console.log(scope) // 'global'
}
checkScope()

而外部作用域不可以访问局部作用域的变量
fucntion checkScope2() {
  var scope = 'global';
}
checkScope2()
console.log(scope) // 报错：scope is not defined
```

## 今天补充的概念： 

## 【1】在函数体内，局部变量的优先级高于同名的全局变量（外层变量）。 如果在函数内声明的一个局部变量或者函数参数中带有的变量和全局变量重名，那么全局变量就会被局部变量所遮盖：

```javascript
var scope = 'global';
fucntion checkScope() {
	var scope = 'lacal';
	console.log(scope) // 'lacal'
}
checkScope()
换句话说就是，在函数内部使用一个变量，它会从最近的作用域开始找，如果局部有就使用局部定于的
如果当前作用域没有，那就会向它的外层作用域查找有没有这个变量，直到找到全局环境，如果全局环境没有找到，
那就会报错了
```

		## 【2】 声明提前 (预编译时执行的)：JavaScript函数里声明的所有变量（但不涉及赋值）都被"提前至函数的顶部"  例子如下：

```javascript
// 还是使用上一个例子， 我做一些修改
var scope = 'global';
fucntion checkScope() {
	console.log(scope) // 输出 "undefined", 而不是"global"
	var scope = 'lacal'; // 变量在这里被赋初始值
  console.log(scope) // 输出 local
}

这里你可能会觉得函数第一行应该打印全局的 "global"，因为代码还没有执行到函数中 var语句，
其实不然，我们结合上一条概念，函数内scope没有使用到全局的scope，
也就是说，在函数体内部变量覆盖了同名全局变量。尽管如此，只有在程序执行到 var 语句的时候，局部变量才被真正赋值
因此，上述过程等价于： 将函数内部的变量声明“提前”至函数体顶部，同时变量初始化留在原来的位置
// 等价的代码如下：
fucntion checkScope() {
  var scope；
	console.log(scope) // 输出 "undefined"
	scope = 'lacal'; // 变量在这里被赋初始值
  console.log(scope) // 输出 “local”
}
```

## 【3】变量提升 和 函数提升的区别 

	### 	变量提升：

```javascript
变量提升就是刚刚上面的例子：
	console.log(global); // undefined
	var global = 'global';
	console.log(global); // global
```

### 	函数提升：

```javascript
console.log(f1); // function f1() {}   
console.log(f2); // undefined  
function f1() {}
var f2 = function() {}
console.log(f2) // function f2() {}

// 这里先思考一下为什么，你自己都可以弄明白 什么是函数提升
// 不懂可以来问我，
```

## 【4】预编译：

###JS并不会完全按照代码顺序进行解析执行，而是在解析之前进行一次“预编译”。在此过程中，会把：

### var、function关键字提前到当前作用域的顶部，变量默认值为undefined，函数默认值为函数体代码块，当函数与变量重名时，保留函数。

### 上面说的 【1】【2】【3】 都是在预编译执行的，我在写一遍：

### 	变量提升：

```javascript
	console.log(global); // undefined
	var global = 'global';
	console.log(global); // global

预编译：
var global;
console.log(global); // undefined
global = 'global';
console.log(global); // global
```

### 	函数提升：

```javascript
console.log(f1); // function f1() {}   
console.log(f2); // undefined  
function f1() {}
var f2 = function() {}
console.log(f2) // function f2() {}
预编译：
function f1() {}
var f2；
console.log(f1); 
console.log(f2); 
f2 = function() {}
```

## 

