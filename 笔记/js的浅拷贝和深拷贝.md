引起浅拷贝和深拷贝问题的原因，本质上，是因为基本数据类型保存在栈内存,而引用类型保存在堆内存中。

为什么要分两种保存方式呢？ 根本原因在于保存在栈内存的必须是大小固定的数据，引用类型的大小不固定，只能保存在堆内存中，但是我们可以把它的地址写在占内存中以供我们访问

浅拷贝
方法一：使用for循环的方法
// 假设有两个对象

var objA = {
  a: 'aa',
  b: 'bb'
};
var objB = {};

// 现在想把对象A的值复制给B，由于对象A的两个值都是原始类型，用浅复制即可

function copy(sub, sup) {
  for (var key in sup) {
    sub[key] = sup[key];
  }
}
copy(objB, objA);

方法二：Object.assign()
兼容性不好
const returnedTarget = Object.assign(source);
方法三：_.clone()

方法四：数组中使用
数组中concat和slice方法

方法五：ES6用法

var arr = [{name:'poetries',age:22}]

var target = [...arr]

深拷贝的用法：
方法一 JSON.parse(JSON.stringify(obj))

方法二 lodash —— _.cloneDeep()
很好地兼容了ES6的新引用类型，而且处理了环型对象的情况

方法三 jQuery —— .clone() /.extend()

方法四 自己实现一个

