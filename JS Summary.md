# JavaScript总结

## JS初步了解
JavaScript是一种具有函数优先的轻量级，解释型或即时编译型的编程语言。虽然它是作为开发Web页面的脚本语言而出名，但是它也被用到了很多非浏览器环境中，JavaScript 基于原型编程、多范式的动态脚本语言，并且支持面向对象、命令式、声明式、函数式编程范式。<br>
JavaScript是一种解释性脚本语言，基于对象不仅可以创建对象也能使用现有的对象，也具有简单，动态性以及跨平台性等特点，是前后端开发的基础。


## JS概要

### 基本语法
标识符是变量、函数、属性的名字，也可以是函数的参数，标识符可以按照第一个字符只能是字母或_或$；其他字符可以是字母、下划线、美元符号或数字。<br>
js中有如下关键字/保留字需要注意break\do\instanceof\typeof\case\else\new\var\catch\finally\return\void\continue\for\switch\while\debugger\function\this\with\default\if\throw\delete\in\try。

### 变量
在JS中变量是松散型，它可以是任何类型的变量，所以在定义变量时最好设置好其类型。<br>
在定义变量的时候要注意使用var操作符，var操作符所定义的变量是局部变量在退出函数后就会被销毁，不使用var定义的变量就是全局变量。

### 操作符
JS中有一元操作符“++ --”，布尔操作符“&& || ！”，&&和||都属于短路操作。在JS中除了false、null、undefined、''、0、NaN，其他都表示为真。算术操作符“+ - * / %”，但是在使用算术操作符运算时要注意JS中可以实现不同类型相加。<br>
例如：<br>
var num1 = 5;<br>
var num2 = 10;<br>
var message = "The sum of 5 and 10 is " + num1 + num2;//输出的结果不是15而是150，因为number类型被转换成了string类型。<br>
JS的关系操作符有“<、> 、<=、>=、 == 、=== 、!=、 !==，JS中的“==”表示同一类型的值相等，“===”表示值和类型都相等。<br>
在JS中比较重要的还有条件（问号）操作符“？：”，这一操作符JS中一般的用法是语句1?语句2：语句3，这个语句代表着当语句1为true时执行语句2，若语句1为flase时，执行语句3。在JS还有一些赋值的操作符“=、 += 、-+ 、*= 、/= 、%=”这些操作符都是给变量赋值时使用。

### JS语句
在JS中有很多常用的语句，我们这里就下列几种的语句，我们通常使用的语句就有下面几种“if、do-while、while for、for-in、for-of、break、continue、switch”，我们就以以下的语句来举例来看语句在JS中的重要性，例如：for-of、forEach这两种能简洁的遍历集合中的元素，for-in主要就是专注于下标，通过标记出数组中下标通过遍历下标来得到我们想要的数，而for-of就是专注于数组中的元素直接遍历元素。最后我们在使用JS中语句的时候一定不要忘记加上{}。

### 函数
在JS中定义函数的时候并不需要指定返回值，并且在JS中函数不会限制传递进来的参数，所以在调用函数时可以传多个参数甚至不进行传参。这是因为JS中的参数在内部是用一个数组来表示的，函数接收到的一直是数组本身，所以并不需要去关注数组中的参数。还要注意的是如果在JS当中定义了两个相同名字的函数的话，JS会只识别后定义的函数。<br>
例如：<br>
function addSomeNumber(num){
    return num + 100;
}<br>
function addSomeNumber(num) {
    return num + 200;
}<br>
console.log(addSomeNumber(100));<br>
上述函数执行下来的话最终值会是300.

### 对象Object
通常将数据和方法封装到对象当中，创建对象可以用new，但是也可以直接添加。虽然object构造函数或对象字面量来创建单个对象，但是这样会导致使用同一个接口创建的对象过多，产生大量的重复代码
例如：<br>
function createPerson(name, age, job)
{<br>
    var o = new Object();<br>
    o.sayName = function(){<br> 
    console.log(this.name);<br>
    };<br> 
    return o;
}<br>


### 数组Array
在JS中，数组可以保存任何类型的数据，并且JS中数组的大小是可以动态调整的，可以根据数据的增加来自动增长。在JS中常用的数组方法有：
元素联合可以在数组中加上我们想要写的：“console.log(xxxx.join(','))；<br>
堆栈方法:栈是一种后进先出的数据结构，栈中的插入和移除都是在栈的顶部去实现的，可以使用push()和pop()两种方法来实现类似于栈的操作。<br>
push()就是从尾端将数据推入到数组当中，pop()就是从末尾推出。<br>
队列方法:队列就是先进先出,为了实现这以操作数组中使用shift(),它将移除数组的第一项并且使得整个数组长度减1，数组中还有unshift() 方法。它能在数组前端添加任意个项并返回新数组的长度。我们需要注意的是push、pop操作在数组末，而 unshift、shift操作在数组头；push、unshift压入而pop、shift弹出。<br>
反数组项reverse():可以使得数组反转以及链接方法concat，在数组中还有一个重要的数组方法splice() ，可以删除数组中任意数量的项，对数组中的数据进行插入，还可以对数组中的数进行替换<br>
例如：<br>
splice(0,2) //删除数组中的前两项，()中指的是要删除的第一项的位置和要删除的项数。
splice(0,0,1) //在第0项后面的位置插入1，()中依次是起始位置、0（要删除的项数）和要插入的项。
splice (2,1,'xx','xxx') //将第三项替换为xx和xxx


### 链式语法
链式语句在实现时只需要让每个函数都返回this来代表该函数的对象，这样能够使得其他函数可以被立即调用。<br>
例如：<br>
var bird = {//定义对象字面量<br>
  catapult: function() {<br>
  console.log( 'Yippeeeeee!' );<br>
  return this;//返回bird对象自身<br>
}


### 闭包
闭包Closure是函数的局部变量集合，但是这些局部变量在函数返回后任然会继续存在，也就是在函数“堆栈”在函数返回之后并不释放内存。
例如：<br>
function greeting(name) {<br>
var text = 'Hello ' + name; // local variable<br>
return function() { console.log(text); }
}<br>
var sayHello = greeting('Closure');<br>
sayHello(); <br>
以上代码执行出来的结果就是Hello Closure，这是因为sayHello指向了greeting函数对象，sayHello()就会对其进行调用，greeting函数执行之后会返回greeting函数内定义的匿名函数对象，而该匿名函数仍然可以访问到了定义在greeting之内的局部变量text。






