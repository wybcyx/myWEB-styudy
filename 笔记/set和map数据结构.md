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