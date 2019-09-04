

# 1、Array 数组类型

## 	除了Object之外，Array类型应该是 JavaScript中最常用的类型了，JavaScript的数组中的每一项，可以保存任意类型的数据，而且数组的大小是可以动态调整的，即可以随着数据的添加自动增长以容纳新增数据

##	创建数组的基本方法有两种。 第一种是使用Array构造函数，如下：

```javascript
var arr = new Array();

如果预先知道数组要保存的项目数量，而该数量会自动变成length属性的值。例如，下面我创建一个length为20的数组
var colors = new Array(20);

也可以向Array构造函数传递数组中应该包含的项。下面我创建包含3个字符串值的数组：
var names = new Array("xiaoming", "陶艳", "大叔")
```

```javascript
当然，给构造函数传递一个值，也可以创建数组，但只传递一个值，它会判断你传的是字符串还是数字，如果是数字，则创建一个所传入数字长度的一个数组，如果传的是字符串，则创建一个包含一个值的数组，如下：
var colors = new Array(3); // 创建了一个包含3项的数组
var names = new Array("大叔"); // 创建了一个包含1项，即字符串为"大叔"的数组
```

```javascript
另外，在使用Array构造函数的时候，也可以省略new操作符。省略new操作符的结果相同:
var colors = Array(3); // 创建了一个包含3项的数组
var names = Array("大叔"); // 创建了一个包含1项，即字符串为"大叔"的数组
```

## 	创建数组的第二种基本方法是使用数组字面量表示法，直接写一对方括号，多个数组项之间以逗号隔开：

```javascript
var arr = []; // 空数组
var names = ["小明", "小勇", "小骆"]; // 三个字符串的数组
var values = [1, 2, ]; // 这样不好，这样会创建一个包含2或3项的数组
var options = [,,,,,] // 不要这样，这样会创建一个包含5或6项的数组
```

## 	读取和修改数组的值，要使用方括号并提供基于0的数组索引，如下：

```javascript
var names = ["小明", "小勇", "小骆"]; 
alert(names[0]); // 显示第一项
names[2] = "小孙" // 修改第三项
names[3] = "小旭" // 新增第四项，length会自动加1
```

##	数组的length属性： length不是只读的，是可以修改的，因此，通过这个属性，可以从数组的末尾移除，或者像数组中添加新项：

```javascript
数组的length属性，长度（个数）
var arr = []; // 空数组
var names = ["小明", "小勇", "小骆"]; // 三个字符串的数组
cosnole.log(arr.length) // 0
cosnole.log(names.length) // 3
```

```javascript
var names = ["小明", "小勇", "小骆"];
names.length = 2; // 修改length，相当于移除了数组第三项
console.log(names[2]); // undefined
```

```javascript
var names = ["小明", "小勇", "小骆"];
names.length = 4; // 修改length，相当于增加了一项，但是增加的那一项没有值
console.log(names[2]); // undefined
```

```javascript
// 通过length来添加有效值
var names = ["小明", "小勇", "小骆"];
names[names.length] = "小旭";
names[names.length] = "小肖";
```

```javascript
var names = ["小明", "小勇", "小骆"];
names[99] = "小旭" // 在位置99上 添加一个名字
这样操作，数组位置3到98实际上都是不存在的，所以访问它们都是undefined
```

## 	检测数组: 使用 typeof 来检测数组，会告诉你数组是一个"object"，要检测数组，需要用到instanceof

```

```

## 	转换方法：所有对象都具有toString()、toLocaleString()、valuesOf()

```

```

## 	栈方法（俗称api）:

```
PUSH.....
```



