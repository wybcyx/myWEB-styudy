对象中的扩展运算符(...)用于取出参数对象中的所有可遍历属性，拷贝到当前对象之中

let bar = { a: 1, b: 2 };
let baz = { ...bar }; // { a: 1, b: 2 }
等价于：
let bar = { a: 1, b: 2 };
let baz = Object.assign({}, bar); // { a: 1, b: 2 }