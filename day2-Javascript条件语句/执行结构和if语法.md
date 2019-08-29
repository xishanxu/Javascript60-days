# 程序执行结构

## 1、顺序结构：按照由上到下的顺序一行一行地执行的程序结构

	## 	2、分支结构：根据不同的条件判断来决定程序执行走向的结构（也叫选择结构）

### if 语句：

```javascript
// if --- 判断逻辑，如果
if(true){
    //会执行的语句
}

if(false){
    //会跳过不执行的语句
}

if(判断条件){ //当if括号中结果为true时执行语句1，否则执行语句2
    //语句1
}else{
    //语句2
}

if(判断条件1){ //当条件1结果为true时执行语句1
    //语句1
}else if(判断条件2){ //当条件1结果为false而且条件2结果为true时执行语句2
    //语句2
}else{ //当条件1条件2结果都为false时执行语句3
    //语句3
}
```

### 在判断条件中，JavaScript 有6种值为假值，剩下的其余所有值都是为真值

### 这6种值分别为： 正负0、null、""、false、undefined 、NaN

```javascript
var a = 2, b = "2";

if(a == b){
    alert("a和b相等");    // 会弹  
}

if(a === b){
    alert("a和b相等");    // 不会弹  
}

if(1 == true){
    alert("数字1是true");
}


if(a = b){
    alert("a和b相等");
}
//一个等号代表赋值操作，结果为等号右边的值
```

### switch语句：

```javascript
// switch  case  多分支语句
// 注意case穿透，要加break语句（如果程序没有发现break语句，那么解析器会继续向下解析）;
switch(语句){  //语句的结果与每一条case内容进行匹配
    case 1:
       alert(1);
       break;
    case 2:
       alert(2);
    	 break;
  	case 3:
    	 alert(3);
       break;
    default:
    	 alert(0);
}
```

```javascript
// 利用 case穿透
switch(i){ 
    case 25:
    // 合并两种情形
    case 35:
       alert("25 or 35");
    	 break;
  	case 50:
    	 alert(50);
       break;
    default:
    	 alert(0);
}
```

```javascript
// 每一个case值不一定是常量，可以是变量，甚至是表达式
switch("Hello World"){ 
    case "Hello" + "World":
    	 alert("bla bla");
       break;
    case "goodbye":
       alert("25 or 35");
    	 break;
  	case 50:
    	 alert(50);
       break;
    default:
    	 alert(0);
}
```

```javascript
switch(num){ 
    case num < 0:
    	 alert("num < 0");
       break;
    case num >= 0 && num <= 100:
       alert("num在0-100之间");
    	 break;
    default:
    	 alert("num > 100");
}
```

## 	3、循环结构：需要重复执行同一操作的程序结构称为循环结构。



练习
点击切换div颜色输入分数，判定成绩等级输入年份，计算某一年是否是闰年输入月份，显示当月的天数             要求：利用case穿透简化代码输入数字，显示星期几，如：输入0，弹出星期日，以此类推（两种方法）设计一个猜拳游戏：      假设： 1代表石头 2代表剪刀 3代表 布      计算机每次随机出现1—3中的任意一个数（parseInt (Math.random()*3) + 1）      玩家也有三种状态，用玩家出的数和计算机出的数进行比对，按照游戏规则比出胜负。


练习
    根据一个数字日期，判断这个日期是这一年的第几天        例如： 20160211，计算后结果为42

制作一个表单，包括用户名，密码，电话要求：1）做好看点2）点击保存按钮时，使用JS判断用户的联系电话是否为纯数字，如果用户输入有错误，使用alert()弹框警告3）判断用户名是否填写，如果空白，使用alert弹框警告4）判断密码长度，必须大于8位，否则alert警告    通过length属性取得字符串的长度    var str = "hello";    str.length // 得到长度





