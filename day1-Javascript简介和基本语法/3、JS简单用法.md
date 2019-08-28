# 1、JavaScript语法

#### 		（1）区分大小写， js的一切都区分大小写 变量名 test 和 Test是两个不同的变量

#### 		（2）标识符 ，（指的是变量、函数、属性的名字或者函数的参数），按照以下规则来组合的字符：

​			I、第一个字符必须是字母、下划线（ _ ）或者一个美元符号（ $ ）

​			II、其他的字符可以是字母、下划线、美元符号 或者 数字

​			III、标识符中的字母也可以包含ASCII或者Unicode字母字符，但是不推荐这么做

#### 		（3）注释： 注释是不被执行的代码

```javascript
// 单行注释

多行注释以/*开头  以*/结尾
/*
*	 这是一个多行注释
*	（块级注释）
*/
```



#### 		（4）严格模式 ES5增加的   script标签中写入 "use strict" 进入严格模式，用得比较少

#### 		（5）js中语句以分号结尾，如果省略了分号，则由解析器自动确定语句的结尾

#### 		（6）多条的语句要组合在一个代码块当中，代码块以 ( { ) 开头，以 ( } ) 结尾 ； 这是C语言的代码风格

```javascript
if (test) {
	test = false;
	alert(test);
}
```

#### 		（7）关键字和保留字  （不能用作标识符）

![](https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1567485019&di=cb2bfbdbbc152475f52e1768634df68c&imgtype=jpg&er=1&src=http%3A%2F%2Fimage.bubuko.com%2Finfo%2F201801%2F20180115212414416857.png)

# 2、向页面输出内容	

```javascript
document.write("hello world");

document.write("<strong>我很man</strong>");

// 转义字符: &lt; || &gt;

document.write("&lt;strong&gt;我很man&lt;/strong&gt;");
```

# 3、变量

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

# 4、变量的类型 (数据类型)

## 	（1） 基本数据类型(简单数据类型)：一共有7种基本数据类型 

#### 			I、String 类型：String 类型用于表示由零或多个 16 位 Unicode 字符组成的字符序列，即字符串 。

#### 			II、Number 类型：JavaScript 中的数字类型只有 Number 一种，Number 类型采用 IEEE754 标准中的 “双精度浮点数” 来表示一个数字，不区分整数和浮点数 。

#### 			III、Boolean 类型： Boolean 类型只有两个字面值：true 和 false 。 在 JavaScript 中，所有类型的值都可以转化为与 Boolean 等价的值。

#### 	IV、Null 类型：Null 是 Javascript 中特殊的原始数据类型，它只有一个值，即 null，字面意思是：“空值”  。它的语义是，希望**表示一个对象被人为的重置为空对象，而非一个变量最原始的状态 。** 在内存里的表示就是，栈中的变量没有指向堆中的内存对象。当一个对象被赋值了 null 以后，原来的对象在内存中就处于游离状态，GC 会择机回收该对象并释放内存。因此，如果需要释放某个对象，就将变量设置为 null，即表示该对象已经被清空，目前无效状态。null 是原始数据类型 Null 中的唯一一个值，但 typeof 会将 null 误判为 Object 类型 。

#### 	 		V、Undefined 类型： Undefined 是 Javascript 中特殊的原始数据类型，它只有一个值，即 undefined，字面意思是：未定义的值 。它的语义是，希望**表示一个变量最原始的状态，而非人为操作的结果 。** 这种原始状态会在以下 4 种场景中出现： 

##### 	如果不理解，可以等后面学了函数，数组在回过来看下面的代码

【1】**声明了一个变量，但没有赋值** 

```javascript
var foo;
console.log(foo); // undefined
```

【2】**访问对象上不存在的属性**

```javascript
console.log(Object.foo); // undefined
var arr = [];
console.log(arr[0]); // undefined
```

【3】函数定义了形参，但没有传递实参

```javascript
// 函数定义了形参 a
function fn(a) {
    console.log(a); //undefined
}
fn(); // 未传递实参
```

【4】使用 void 对表达式求值		

```javascript
void 0 ; // undefined
void false; // undefined
void []; // undefined
void null; // undefined
void function fn(){} ; // undefined
```

#### VI、第六种基本数据类型是 ES6增加的  Symbol 类型：它的字面意思是：符号、标记。代表独一无二的值 。在 ES6 之前，对象的属性名只能是字符串，这样会导致一个问题，当通过 mixin 模式为对象注入新属性的时候，就可能会和原来的属性名产生冲突 。而在 ES6 中，Symbol 类型也可以作为对象属性名，凡是属性名是 Symbol 类型的，就都是独一无二的，可以保证不会与其他属性名产生冲突。

```javascript
// 和其他基本类型不同的是，Symbol 作为基本类型，没有对应的包装类型，也就是说 Symbol 本身不是对象，而是一个函数。因此，在生成 Symbol 类型值的时候，不能使用 new 操作符 。
var s = Symbol(); //s是独一无二的值
typeof s ; // symbol　　
```

#### VII、 第七种数据类型是 2019新增的 ，BIgInt 类型：可以表示大于 253 的整数。而在Javascript中，[`Number`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number) 基本类型可以精确表示的最大整数是 2^25。**BigInt** 可以表示任意大的整数。 了解一下就行

## （2）、复杂数据类型（引用类型）：

	### 	在JS当中引用类型只有一种， Object类型，其中有一种特殊的对象 叫做Function（函数类型）

## （3）、typeof 操作符

### 	typeof可以直观的来区分一个变量是什么数据类型， typeof的返回值是你所判断的那个变量的类型的**字符串**  他有两种写法 ：typeof 37 或者 typeof(37)

```javascript
// typeof 一共有8种返回值
typeof 37; //==>'number' 
typeof 42n; //==> 'bigint'
typeof 'bla'; //==>'string';
typeof true; // ==> 'boolean';
typeof Symbol() //==> 'symbol';
typeof undefined //==>'undefined';
typeof {a: 1} //==> 'object';
typeof [1, 2, 4] //==> 'object'; 注意 数组也是object类型
typeof function() {} //==> 'function'; 特殊的对象类型
```

# 5、运算符

## 	算数运算符：加、减、乘、除、求余/取模（+ 、- 、* 、/ 、%）

```javascript
/*余数： a/b整除之外的剩余的数字
10 / 3 = 3 ... 1
10 % 3 = 1
3 % 10 = 3
取余：大数对小的那个数取余结果为整除之后的余数
    小的那个数对大数求余的结果就是小的那个数本身 */
// 其中加操作符 除了可以进行数字相加 也可以做 字符串的拼接
var a = 1, b = 2;
	a + b // => 3

var a = "aa", b = "cc";
	a + b // => "aacc"

var a = "1", b = 3; //这里涉及到变量的类型隐式转换，等下要讲
	a + b // => "13"
```

## 	关系运算符:  

​		==（相等） 、!=（不等于）、<（小于） 、>（大于） 、<=（小于或者等于） 、>=（大于或者等于）

```javascript
  // 判断运算符两侧的结果是否满足规则，满足结果即为true，否则false
		5 != 3    // true
    5 < 3     // false
		5 <= 5   //true
```

```javascript
/*  = 和 == 以及 === 的区别
    一个等号是赋值，将等号右边的值赋给左边
    两个等号是判断相等，相等结果为true，不等为false，不考虑数据类型，只判断值
    三个等号要求全等，不仅值要相等，类型也必须相等 */

var a = 2, b = “2”;
a == b  // true
a === b // false
```

## 	逻辑运算符：

```javascript
var a = 2, b = 5
// 逻辑与：&&  “和”的意思
// 必须两个条件均为true结果才为true
var res = a < 10 && b < 10  // true
var res = a > 10 && b < 10  // false

// 逻辑或：||   “或者”的意思
// 只要有一个条件为true结果就为true
// 必须两个条件均为false结果才为false
var res2 = a < 10 ||  b > 10 // true
var res2 = a > 10 || b > 10 // false


// 逻辑非：!  “不”的意思
// 对本身的结果取反
var a = true; 
var res = !a; // false

```

## 运算符的简写:

```javascript
  赋值运算简写

   +=、-=、*=、/=

   a = a + 1      a += 1
   a = a  - 1      a  -= 1
   a = a  * 1      a  *= 1
   a = a  / 1      a  /= 1
  
   a++    a += 1     a = a + 1
   a--      a  -= 1     a = a -  1

	 // 自增和自减 
   ++a    --a
   var a = 10;
   console.log(a++);     10
   console.log(a);          11 
   console.log(++a);     12
    
   // 自增自减前置后置是不一样的，前置是先加后用，后置的先用后加。

   var k=0;  
	console.log(k++ + ++k +k +k++);  // 6
	console.log(k); // 3
```

# 6、 变量的类型转换

## 隐式转换：

```javascript
var a = 2, b = “2”;
a + b  ===  "22"
a == b  true
//  使用双等号进行变量对比的时候 变量会进行隐式转换
```

### 隐式转换中主要涉及到三种转换：

#### 1、将值转为原始值，ToPrimitive()。

#### 2、将值转为数字，ToNumber()。

#### 3、将值转为字符串，ToString()。

```javascript
1、若 x 为 null 且 y 为 undefined， 返回 true。
2、若 x 为 undefined 且 y 为 null， 返回 true。
3、若 Type(x) 为 Number 且 Type(y) 为 String，返回比较 x == ToNumber(y) 的结果。
4、若 Type(x) 为 String 且 Type(y) 为 Number，返回比较 ToNumber(x) == y 的结果。
5、若 Type(x) 为 Boolean， 返回比较 ToNumber(x) == y 的结果。
6、若 Type(y) 为 Boolean， 返回比较 x == ToNumber(y) 的结果。
7、若 Type(x) 为 String 或 Number，且 Type(y) 为 Object，返回比较 x == ToPrimitive(y) 的结果。
8、若 Type(x) 为 Object 且 Type(y) 为 String 或 Number， 返回比较 ToPrimitive(x) == y 的结果。
9、若 Type(x) 与 Type(y) 相同， 则

    I* 若 Type(x) 为 Undefined， 返回 true。
    II* 若 Type(x) 为 Null， 返回 true。
    III* 若 Type(x) 为 Number， 则
  
        (1)、若 x 为 NaN， 返回 false。
        (2)、若 y 为 NaN， 返回 false。
        (3)、若 x 与 y 为相等数值， 返回 true。
        (4)、若 x 为 +0 且 y 为 −0， 返回 true。
        (5)、若 x 为 −0 且 y 为 +0， 返回 true。
        (6)、返回 false。
        
    IV* 若 Type(x) 为 String, 则当 x 和 y 为完全相同的字符序列（长度相等且相同字符在相同位置）时返回 true。 否则， 返回 false。
    V* 若 Type(x) 为 Boolean, 当 x 和 y 为同为 true 或者同为 false 时返回 true。 否则， 返回 false。
    VI*  当 x 和 y 为引用同一对象时返回 true。否则，返回 false。

10、否则返回 false。
```

```javascript
// 这是一个比较复杂的例子
[] == !{}
//
1、! 运算符优先级高于==，故先进行！运算。
2、!{}运算结果为false，结果变成 [] == false比较。
3、根据上面第7条，等式右边y = ToNumber(false) = 0。结果变成 [] == 0。
4、按照上面第9条，比较变成ToPrimitive([]) == 0。
    按照上面规则进行原始值转换，[]会先调用valueOf函数，返回this。
   不是原始值，继续调用toString方法，x = [].toString() = ''。
   故结果为 '' == 0比较。
5、根据上面第5条，等式左边x = ToNumber('') = 0。
   所以结果变为： 0 == 0，返回true，比较结束。
```

## 显式转换：

#### parseInt()、parseFloat()、Number()、toString()、String()

#### toFixed()保留几位小数之后数据类型变为字符串

```javascript
parseInt(string, radix)   将一个字符串 string 转换为 radix 进制的整数， radix 为介于2-36之间的数。

parseFloat(value) 将一个值 转换为 浮点数。

Number() 将一个值 转换为 数字。

toString()方法；数值、字符串、对象、布尔；都有toString方法；这个方法唯一能做的就是返回相应的字符串；其中null和undefined没有toString()方法；

String()属于强制转换， null转换的结果为null；undefined转换的结果为undefined；其余的如果有toString()方法，即调用该方法，返回相应的结果；
```

```javascript
    parseInt() 方法首先查看位置 0 处的字符，判断它是否是个有效数字；如果不是，该方法将返回 NaN，不再继续执行其他操作。 但如果该字符是有效数字，该方法将查看位置 1 处的字符，进行同样的测试。这一过程将持续到发现非有效数字的字符为止，此时 parseInt() 将把该字符之前的字符串转换成数字。

parseInt("20b") == 20

parseInt("b20") == NaN

parseInt("20.99") == 20

另：Math.round() 方法可以实现四舍五入  

Math.round(20.6) == 21

Math.round("20.6") == 21

Math.round("20.6r") == NaN

    parseFloat()跟parseInt()极其相似，不过第一个出现的小数点是有效字符。如果有两个小数点，第二个小数点将被看作无效的。parseFloat() 会把这个小数点之前的字符转换成数字。

parseFloat("11.22.33") == 11.22
```

```javascript
NaN：Not a Number
     是一个特殊值，说明某些算术运算（如求负数的平方根）的结果不是数字（本来期望得到一个数字，但是结果没有计算成功）。方法 parseInt() 和 parseFloat() 在不能解析指定的字符串时就返回这个值

// isNaN(num)函数，该函数判断num变量的值是否是NaN，是NaN返回true，数字返回false

ECMAScript 中可用的 3 种强制类型转换如下：
Boolean(value) - 把给定的值转换成 Boolean 型；
Number(value) - 把给定的值转换成数字（可以是整数或浮点数）；
String(value) - 把给定的值转换成字符串；

```

# 作业：

1．计算两个文本框的和

2．var k=0;  console.log(k++ + ++k +k +k++)

3．掌握逻辑运算的意义

4．掌握八进制、十六进制的写法

5．掌握NaN的含义

6．掌握Number函数的转换结果

7．计算两个文本框的加减乘除

要求：1) 使用parseInt方法类型转换

​          2) 计算结果使用Math.round方法四舍五入





