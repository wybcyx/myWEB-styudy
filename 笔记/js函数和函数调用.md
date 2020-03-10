1、js目前6中函数的调用方式：
一般函数--》this指向window
构造函数--》this指向对象实例
对象的方法函数 --》this指向调用方法的实例对象
绑定事件函数--》this指向绑定事件对象
定时器函数---》window
立即执行函数---》window
2、改变函数内部的this指向
call（）
作用：调用函数和改变函数内部的this的指向
用法：fun.call(thistarge,param1,....)
thistarge--->想要this指向的对象
param：参数
在出现ES6的classheextends之前，就是使用call（）实现的js继承；


apply（）
功能和用法都类似call，不过参数是包含在数组中的；
apply还有个作用，利用他的参数是数组的原理，调用math.max（）方法求数组的最大最小值

bind（）
(1)不会立即调用函数，改变this的指向
（2）返回值是原函数改变this之后的新函数
（3）如果有的函数需要改变函数内的this指向，但是又不需要立刻执行，例如setTimeout()定时函数，既可以使用bind（）
实例操作：假如有一个按钮，点击后三秒钟内不可用，三秒后启用？
 





