1.
    // 1.通过class关键字创建类，类名的首字母大写
    // 2.类里面的constructor是构造函数，可以接受参数，返回类的实例对象
    // 3.使用new生成实例时就会调用类的构造函数，返回对象实例
    // 4.生成实例时new不能省略
    // 5.注意语法，创建class时类名后边没有（），使用new生成实例的时候，类名后边带（）
    // 构造函数不需要function关键字
2.类的继承
class 通过extends可以完成继承的操作
super关键字可以是子类访问父类的函数，构造函数和普通函数都可以。
在继承当中，当一个实例调用方法时，首先看看子类中是否存在这个函数，若果不存在去父类中寻找。（原型链的原理）
注意：子类中，使用super调用构造函数或者普通函数，super必须放在this之前。


ES6的使用需要注意三个点：
（1）类是没有变量提升的，所以在使用类之前，必须先定义；
（2）类的共有属性和发方法一定要加this;
(3)类里的指向问题
constructor中this指向的是对象实例
在类中的方法在被调用时，this的基本原则就是谁调用，指向谁；（实例调用就是实例，button调用，this就是button）
某些时候，可以定义that存储this的内容，方便使用；

3.构造函数和原型
面向对象编程（OOP）都是存在类的概念的，java，c、c++等。类是模板，通过类创建实例化对象；
在ES6之前的javascript是没有类的概念的，js创建对象都是使用的构造函数生成的；
创建对象的三种方法：
(1)字面值的方法
（2）new Object（）
（3）自定义构造函数的方法

构造函数：是一类特殊的函数，用来初始化对象，为对象成员赋值，他总是和new一起创建对象；
在ES6之前我们将可以将公共方法和属性封装到一个函数中，这就是构造函数。

构造函数的使用注意的地方：
和new一起使用，才行
首字母大写

new和构造函数一起是都做了什么？
首先创建一个新的空对象；
将this指向这个空对象；
执行构造函数中的代码，给新对象属性和方法；
最后返回这个对象实例；


构造函数有什么缺点？-----浪费内存
解决方法：将代码和作用相同的类函数使用protoType，也是构造函数原型定义；
构造函数通过原型分配的函数是所有对象共享    的；
问：原型是什么？
是个对象，构造函数的prototype属性被叫做原型对象，其实 对象的_proto_属性也是指向原型对象
问：原型有什么作用？
提供共享方法 ，节省内存空间


对象为什么也可以使用原型上的方法呢？
因为对象实例有个__proto__属性，他指向构造函数的原型
实例的__proto__和构造函数的prototype是严格相等的；
  

实例的方法查找规则：
首先查找实例本身是否有这个方法===》如果没有，因为__proto__的存在，就去原型对象上去寻找。


对象原型的属性constructor函数指向的是构造函数本身；

this的指向问题？
this只有在调用的时候才能确定指向，谁调用就指向谁。构造函数中的this指向对象实例，
4.继承
在ES6之前是没有class和extends来实现继承的，js使用构造函数+原型对象来完成继承，我们叫做“组合继承”

    4.1 call（）
    作用：1、调用函数，2、修改函数运行的this的指向；
    用法：function.call(thisarg,arg1,arg2....);
    thisarg====>当前调用函数this的指向函数
5.ES5新增的方法
数组新增的方法：
forEach()、map()、filter()、some()、every()
字符串新增的方法：
trime
对象的方法：
Object.keys()用于获取对象自身所有的属性，返回值为属性的数组





