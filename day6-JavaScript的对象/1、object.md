# 1、object：

	## 	创建object实例的方式有两种。 第一种是使用 new 操作符后面跟Object构造函数：

```javascript
var person = new Object();
person.name = "xuge";
person.age = 15;
```

## 	另一种是使用对象字面量表示法，对象字面量是一种定义对象的简写形式，目的在于简化创建包含大量属性的对象的过程：

```javascript
var person = {
	name: "xuge",
	age: 15
}
```

## 	使用对象字面量语法时，属性名可以使用字符串或者数字：

```javascript
var person = {
	"name": "xuge",
	"age": 15,
  5: true // 对象的键（属性名）也可以是数字，但是尽量不要这样写。后面会说明原因
}
```

## 	像函数传递大量科学参数时，可以使用对象字面量多方式（首选）：

```javascript
function displayInfo(agms) {
  var str = ''
  if(agms.name) {
     str += "Name:" + agms.name
  }
  if(agms.age) {
     str += "Age:" + agms.age
  }
  alert(str)
}
displayInfo({ // 传递一个对象字面量到函数中
  name: "xiongda",
  age: 99
})
displayInfo({
  name: "dingding"
})
```

## 	访问对象的属性：访问对象的值有两种方式

### 		第一种，是通过一个点( . )来访问

```javascript
var obj = {
	name: "xuge",
	age: 15,
  5: "123"
}
console.log(obj.name) // xuge
console.log(obj.age) // 15

```

		### 		第二种访问方式，是使用 中括号 [] 来访问：

```javascript
var obj = {
	name: "xuge",
	age: 15
}
console.log(obj["name"]) // xuge
console.log(obj["age"]) // 15
```

```javascript
// []这种方式来访问，有什么用呢？？？很有用 重点
var obj = {
	name: "xuge",
	age: 15,
  5: "hahaha"
}
// 我这个时候定义一个 变量 a ，它的初始化值 为 name
var a = "name" 
// obj.a 这样做的话，我们是去obj里访问 a 这个属性的值，并不是去找name的值
// 所以 如果是一个变量，或者是数字,都要用中括号的方式去取 ，obj.5 这样会报错
console.log(obj[a]) // 旭哥
console.log(obj[5]) // "hahahah"

// 还有如何你在obj里面的属性写了，包含导致语法错误的字符，或者使用了保留字等
// 也可以用中括号来访问，对象值
var obj = {
  "first name": "xiaoxuxu"
}
obj["first name"] // xiaoxuxu
```

# 2、Object常用的几个API：

```javascript
Object.keys(obj)    // 返回的一个数组
// simple array
var arr = ['a', 'b', 'c'];
console.log(Object.keys(arr)); // console: ['0', '1', '2']

// array like object
var obj = { s: 'a', f: 'b', g: 'c' };
console.log(Object.keys(obj)); //console: ["s", "f", "g"]
```



