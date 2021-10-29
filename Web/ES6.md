## ECMA Script

#### 变量

##### 变量修饰符

###### let

+ let 只能声明一次，不能重复声明

###### const

+ const 被定义将不能被重新赋值

##### 解构表达式

###### 数组解构

~~~js
let arr=[1,2,3]
let [a,b,c]=arr;
~~~



###### 对象解构

~~~js
const ps={
    t1:1,
    t2:2,
    t3:3
}

let {t1,t2,t3}=ps
let {t1:name,t2,t3}=ps //不同名字

~~~

#### 字符串

##### 字符串方法拓展

ES6 之前判断字符串是否包含子串，用 indexOf 方法，ES6 新增了子串的识别方法。

- **includes()**：判断是否找到参数字符串。

- **startsWith()**：判断参数字符串是否在原字符串的头部。

- **endsWith()**：判断参数字符串是否在原字符串的尾部

- **repeat()**：返回新的字符串，表示将字符串重复指定次数返回。

  

##### 字符串模板

通过反引号包裹字符串可以多行输入，插入变量和表达式

~~~js
let a=11
let b=111
let c=`${a} 

is ${b}`
~~~

#### 函数

##### 默认值

~~~js
function a(arg1=11,arg2){
    
}
~~~

##### 箭头函数

~~~js
//一个参数
a=>console.log(a);
//返回
a=>a--;

()=>a--

//多个参数
(a,b)=>{
	console.log(a)
}


~~~

#### 对象

##### 属性名表达式

ES6允许用表达式作为属性名，但是一定要将表达式放在方括号内。

~~~js
const obj = { 
    ["he"+"llo"](){
        return "Hi";  
    }
}
obj.hello();  //"Hi"
~~~



##### 对象的拓展运算符

拓展运算符（...）用于取出参数对象所有可遍历属性然后拷贝到当前对象。

~~~js
let age = {age: 15};
let name = {name: "Amy"};
let person = {...age, ...name};
person;  //{age: 15, name: "Amy"}
~~~

#### 对象新方法

+ **keys()** 获取对象key数组
+ **values()** 获取values数组
+ **entries()** 获取以'[[key 1,value 1],[key 1,value 1]...]形式的数组
+ **map()** 对目标进行枚举，将原对象所有元素处理后返回新对象
+ **reduce()**对目标进行枚举，回调函数的参数为上一次返回的结果，常用于数组求和等等



#### Promise 对象

##### 概述

是异步编程的一种解决方案。

从语法上说，Promise 是一个对象，从它可以获取异步操作的消息。

##### 示例

~~~js
function get(url,data){
  return  new Promise((resolve,reject)=>{
        axios.post(url,params)
       .then(res=>{
            if(res.data){
                resolve(res.data);
            }else{
                
            }
        }).catch(err =>{
            reject(err.data)
        })
   })
}

get("/user/login",xxx)
    .then(data=>{
    	console.log("登录成功")
    	return get("/user/price",xxx)
    })
	.then(data=>{
    	console.log("查询成功")
    	return get("/user/pay",xxx)
    })
	// ======
	.catch(err=>{
    	console.log(err)
	})


~~~



#### 模块化

##### 基本使用

~~~js
# ./user.js

var name="jack"
var age=11
function add(a+b){
    return a+b
}
export {name,age}
#end

# ./main.js

import {name,add} from './user.js'

add(1,2)
~~~

##### default

~~~js
# ./user.js

export default  add(a+b){
    return a+b
}
#end

# ./main.js
import abc from './user.js'

abc(1,2)

~~~