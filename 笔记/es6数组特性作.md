数组和伪数组？
    伪数组具有数组的length和按照index遍历的方法，但是不具有数组的push、pop的方法

维数组转化为数组的方法？
    1、使用拓展符号
    var divs=document.querySelecter("div")//这个结果返回的就是一个维数组
    var arr=[...divs]//这就是转化后的数组，他有push、pop等数组常用的方法函数
    2、使用es6的新方法Array.form（）
    var arr2=Array.form（divs）//
    3、使用es5的方法
    var srr3=[].slice.call(divs)


数组的常用场景和问题
    1、数组的合并
    let a=[1,2,3];
    let b=[4,5,6]
    第一种方法
    let c = a.concat(b);
    第二种方法
    for(let i in b){
    　　a.push(b[i])
    }
    第三种办法
    a.push.apply(a,b);

    第四种办法
    var newA = [...a,...b];console.log(newA)


 
数组的去重
 // 方法1、利用set数据结构去重,es6的新特性
        <!-- // console.log("利用set数据结构去重:",[...new Set(arr)])
        // console.log("利用set数据结构去重:",arr)
        // 方法2、利用for嵌套for，然后splice去重
        // function unique2(arr){            
        //     for(var i=0; i<arr.length; i++){
        //         for(var j=i+1; j<arr.length; j++){
        //             if(arr[i]==arr[j]){         //第一个等同于第二个，splice方法删除第二个
        //                 arr.splice(j,1);
        //                 j--;
        //             }
        //         }
        //     }
        //     return arr;
        //     }
        //     var copy_arr=[...arr]
        // console.log("方法2利用for循环嵌套和数组的方法splice",unique2(copy_arr));
        // console.log("方法2利用for循环嵌套和数组的方法splice",arr);
        // end

        // 方法3、利用数组中的indexOf（）方法
        // 新建一个空的结果数组，用来保存结果。
        // 遍历数组中的元素，如果这个元素在新数组中存在就跳过，不存在就push进新数组
            // function unique3(arrParams) {
            //     if(!Array.isArray(arrParams)){
            //         console.log("error arr");
            //         return
            //     }
            //     var resultArr=[];
            //     for (let index = 0; index < arrParams.length; index++) {
            //         if(resultArr.indexOf(arrParams[index])=== -1){
            //             resultArr.push(arrParams[index]);
            //         } 
            //     }
            //     return resultArr;
            // }
            // console.log("方法3利用数组中的indexOf（）方法",unique3(arr));
            // console.log("方法3利用数组中的indexOf（）方法",arr);
            // 方法4：利用数组的sort方法进行排序，循环判断相邻元素
            // function unique4(arrParams) {
            //     if(!Array.isArray(arrParams)){
            //         console.log("error arr");
            //         return "";
            //     }
            //     arrParams=arrParams.sort();
            //     var resultArr=[arrParams[0]];
            //     for (let index = 1; index < arrParams.length; index++) {
            //         if (arrParams[index-1]!=arrParams[index]) {
            //             resultArr.push(arrParams[index])
            //         }
            //     }
            //     return resultArr;
            // }
            // console.log("方法4:利用数组中的sort（）方法",unique4(arr));
            // console.log("方法4:利用数组中的sort（）方法",arr);
            // 方法5、利用数组的include方法和indexof类似
            // 方法6、利用Map数据结构去重


es6新增的方法Array.form()
    Array.from方法用于将两类对象转为真正的数组：类似数组的对象（array-like object）和可遍历（iterable）的对象.(包括 ES6 新增的数据结构 Set 和 Map）。

    实际应用中，常见的类似数组的对象是 DOM 操作返回的 NodeList 集合，以及函数内部的arguments对象。
    // NodeList对象
    let ps = document.querySelectorAll('p');
    Array.from(ps).filter(p => {
    return p.textContent.length > 100;
    });

    // arguments对象
    function foo() {
    var args = Array.from(arguments);
    // ...
    }
Array.of()新方法
    Array.of方法用于将一组值，转换为数组。

    Array.of基本上可以用来替代Array()或new Array()，并且不存在由于参数不同而导致的重载。它的行为非常统一。
    Array.of() // []
    Array.of(undefined) // [undefined]
    Array.of(1) // [1]
    Array.of(1, 2) // [1, 2]
es6内置的数组方法find（）
    用于查找第一个符合条件的数组元素
    方法的参数是一个函数,返回的是符合条件的数组元素，查询不到，返回undefined
    arr.find((item,index)=>{
        return ...;
    })
es6内置的数组方法findindex（）  
    用于查找第一个符合条件的数组元素的索引 
    方法的参数是一个函数,返回的是符合条件的元素索引，查询不到，返回-1
es6内置的数组方法include（）  
    查找数组中是否存在给定的元素，返回布尔值
