# 5th
#### 条件语句  
if…else  
switch  
三无运算符  
#### 循环  
for循环  
break退出循环  
continue跳出迭代  
while/do…while  
#### 函数  
一些内置函数：  
* console.log()  
* Math.random()生成一个随机数   

**自定义函数**  
```
function draw(){  
  ctx.clearRect(0,0,WIDTH,HEIGHT);  
  for (var i = 0; i < 100; i++) {  
    ctx.beginPath();  
    ctx.fillStyle = 'rgba(255,0,0,0.5)';  
    ctx.arc(random(WIDTH), random(HEIGHT), random(50), 0, 2 * Math.PI);  
    ctx.fill();  
  }  
 }   
```
**调用函数**  
要在函数定义之后，通过将函数名后跟圆括号  
**匿名函数**  
没有函数名
```
myButton.onclick = function() {  
  alert('hello');  
}  
```
也可以分配变量值  
```
var myGreeting = function() {  
  alert('hello');  
}  
```
其调用方法myGreeting()  
**函数参数**  
#### 事件  
onclick/onfocus/onblur/ondbclick/onkeypress/onkeydown/onkeyup/onmouseover/onmouseout等  
**事件监听器**  
addEventListener()和removeEventListener()  
给同一个监听器注册多个处理器  
```
myElement.addEventListener('click', functionA);  
myElement.addEventListener('click', functionB);  
```
事件对象  
#### 对象  
一个对象由许多成员组成，可将一个对象作为另一个对象的成员  
点表示法person.name.first  
括号表示法person['name']['first']  
**this** 指向运行代码时的对象  
**object()构造函数**  
var person1 = new Object();在变量中存储一个空对象，然胡根据需要添加属性和方法  
**create()**  
基于现有对象创建新对象var person2 = Object.create(person1);  
**对象原型**  
**prototype**  
继承成员被定义的地方，与this区分  
**constructor**  
person1.constructor.name可获取对象构造器名字  
**修改原型**  
构造器质保函属性定义，方法分装在不同代码块  
#### 继承  
```
function Person(first, last, age, gender, interests) {  
  this.name = {  
    first,  
    last  
  }；
  ……
  }
```
创建Teacher()类，继承已有Person的成员，并添加新的属性subject和一个更新的greeting()方法  
```
function Teacher(first, last, age, gender, interests, subject) {  
  Person.call(this, first, last, age, gender, interests);  
  this.subject = subject;  
}  
```
call()函数调用别处函数，this指定运行函数时的值，最后添加一个新的subject属性  
```
Teacher.prototype.greeting = function() {……}  
```
添加新的greeting函数  
**设置Teacher()原型和构造器引用**  
Teacher.prototype = Object.create(Person.prototype);  
create()创建一个和Person.prototype一样的原型属性值，将其所有的属性和方法继承给Teacher.prototype  
而此时Teacher()的constructor属性是指向Person()的，改变如下：  
Teacher.prototype.constructor = Teacher;  




