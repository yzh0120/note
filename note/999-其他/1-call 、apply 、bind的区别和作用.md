call、apply和bind都是JavaScript中改变函数内部this指向的方法。
call和apply会立即调用函数，而bind则返回一个新的函数。
call接受参数按位置传递，
apply参数需以数组形式传递。
bind常用于延迟执行并改变this，如在定时器场景中。
apply常用于处理数组，如获取数组最大值(展开第二个参数的特性)。call则常用于实现继承。

## call
function Person(uname,age){
    this.uname = uname
    this.age = age
}
function Son(uname,age){
    Person.call(this,uname,age)
}
var son = new Son("zhang",12)
console.log(son)


## 利用 apply() 会展开第二个参数的特性，效果等同于 ...[1,2,3] 展开运算符
Math.max.apply([],[2,6,8,3,4,9,7,23,56,889])

## bind()判断数据类型
fun.bind(this, arg1, arg2, arg3, arg4, ...)
let obj = {
    user: 'test',
}
let funA = function(arg1, arg2, arg3){
    console.log(this.user)  // test
    console.log(arg1, arg2, arg3)  // 10,1,2
};
let funB = funA.bind(obj, 10)
funB(1, 2)
