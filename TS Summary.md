# TypeScript总结

## TypeScript和JavaScript
TypeScript 是一种由微软开发的自由和开源的编程语言，它是 JavaScript 的一个超集，扩展了 JavaScript 的语法，typescript能够编译成JavaScript。
TypeScript 可以处理已有的 JavaScript 代码，并只对其中的 TypeScript 代码进行编译。由于typescript大部分跟JavaScript一样，所以只阐述有区别的地方。


### 安装
使用国内镜像：
npm config set registry https://registry.npmmirror.com<br>
安装 typescript：npm install -g typescript<br>
查看版本号：tsc -v<br>
安装成功

### let 和 const
使用let或const申明变量，并加上类型说明，作用域为块级，即以{}为界。<br>
例如：<br>
let firstname:string = 'Bob';//即声明了一个string类型的变量firstname，并为其赋值为Bob<br>
let age = 1;//声明了一个名为age的变量，ts会自动为其匹配类型<br>
const pi: number = 3.14;//const的作用是设置为常量，值不能改变

### 数组解构
将数组的值单个或多个提取出来
例如：<br>
let input = [1,2,3,4];<br>
let [first,second]=input;<br>
console.log(first);//输出1<br>
console.log(second);//输出2<br>
let [one,...others]=input;<br>
console.log(...others);//输出2,3,4<br>
let new =[0,...others,5];<br>
console.log(new);//输出0，2，3，4，5

### 函数
函数声明告诉编译器函数的名称、返回类型和参数,函数定义提供了函数的实际主体。<br>
例如：<br>
function add(x: number, y: number): number {
  return x + y;
}//定义了一个拥有完整的参数和返回类型的函数，不使用时，TS可以自动进行类型推断<br>

function greeting(firstName: string, lastName?: string) {<br>
  if(lastName) {<br>
      return `Hello ${firstName} ${lastName}!`;<br>
  }
  return `Hello ${firstName}!`;
}//定义了一个带有可选参数的函数，可选参数必须放在必要参数后

function greeting(firstName: string, lastName = 'Kirk') {
  return `Hello ${firstName} ${lastName}!`;
}//定义了一个含有默认参数的函数

let ffff= () => 'hello world'；//箭头函数，简化函数定义

### 类class
TypeScript 是面向对象的 JavaScript。类描述了所创建的对象共同的属性和方法。TypeScript 支持面向对象的所有特性，比如 类、接口等。与c++的类class类似。<br>
例如：<br>
class person{<br>
    public name:string;//公有属性<br>
    private _age:number;//私有属性<br>
    static address;//静态属性,可直接使用而不需要实例化<br>
    constructor(name: string, weather: string){ 
    this.name=name;<br>
    this._age=age;<br>
  }//构造函数<br>
  get name()：number{
    return this._age;
  }//编写接口，便于外部调用
}

class son extends person{//使用extends继承类
}

### 模块化
编写多个.ts文件，每个.ts文件都是一个模块，通过 export 来对外部模块暴露元素， import 来引入模块。