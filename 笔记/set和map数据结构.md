1、set
Es6提供了新的数据结构set，类似于数组，但是set的值是唯一的，不重复；
1.1
Set本身是一个构造函数，用来生成 Set 数据结构。
    const s = new Set();
    [2, 3, 5, 4, 5, 2, 2].forEach(x => s.add(x));
    //遍历数组向set对象添加数据的时候，重复的数据是不会添加进去的
    for (let i of s) {
    console.log(i);
    }
    // 2 3 5 4
1.2
Set函数可以接受一个数组（或者具有 iterable 接口的其他数据结构）作为参数，用来初始化。 
set数据结构在添加数据是使用add，但是set的add是不会进行格式转换的，5和‘5’是不相同的，类似用===（严格等于）。但是set在add是NaN判断是重复值的。（===判断NaN是false）

两个对象总是不相等的。例如：
let set = new Set();

set.add({});
set.size // 1

set.add({});
set.size // 2

set的属性和方法
属性：size类似数组的length
方法：
s.add(1).add(2).add(2);
// 注意2被加入了两次
//向set中添加数据
s.size // 2
//
s.has(1) // true，判断是否存在该value
s.has(2) // true
s.has(3) // false

s.delete(2);//删除set中的某个value值
s.has(2) // false
//Set.prototype.clear()：清除所有成员，没有返回值。

Array.from方法可以将 Set 结构转为数组。
总结一波：
数组转set：new set(arr)
set转数组：Array.from(mySet)


set的实例还有一些便利方法：
set.keys()//返回键
set.values()//返回值
set.entries()//返回键值对，set的键和值是一样的。
set.forEach((value,key)=>{},this)//forEach其实还有第二个参数，表示绑定处理函数内部的this对象。

2.WeakSet 
weakSet和Set的作用是类似的，但是WeakSet的元素必须是对象，如果插入值类型的会报错。

3.Map
JavaScript 的对象（Object），本质上是键值对的集合（Hash 结构），但是传统上只能用字符串当作键。这给它的使用带来了很大的限制。

Map类似于javascript中的Objection，但是“键”的范围不在仅仅限于字符串。Map的键可以使任何类型的值；

      var arr=[["name","wangyongbo"],["age","23"]]
        var map=new Map(arr);
        console.log(map);
        console.log(map.get("name"));
        map.set(123,"wywww")
        console.log(map);

如果对同一个键多次赋值，后面的值将覆盖前面的值。

注意，只有对同一个对象的引用，Map 结构才将其视为同一个键。这一点要非常小心。
const map = new Map();

map.set(['a'], 555);
map.get(['a']) // undefined

上面代码的set和get方法，表面是针对同一个键，但实际上这是两个不同的数组实例，内存地址是不一样的，因此get方法无法读取该键，返回undefined。


Map 的键实际上是跟内存地址绑定的，只要内存地址不一样，就视为两个键。这就解决了同名属性碰撞（clash）的问题，我们扩展别人的库的时候，如果使用对象作为键名，就不用担心自己的属性与原作者的属性同名。

map实例的属性和方法
size=>map实例的长度，相等于length
set（key，value）=》向map中添加元素，该方法返回的是map实例，因此可以使用链式操作
has（key）//返回布尔，表示某个键是map实例中是否存在
delete（key） ====删除map中的某个键
clear（） ====清空map实例


遍历方法（map的遍历顺序就是元素的插入顺序   ）
Map.prototype.keys()：返回键名的遍历器。
Map.prototype.values()：返回键值的遍历器。
Map.prototype.entries()：返回所有成员的遍历器。
Map.prototype.forEach()：遍历 Map 的所有成员。

map转数组的方法====》运算扩展符（...）


