##  ES6之前是没有引入类的概念，所以JavaScript是直接通过构造函数来创建实例的
构造函数：通过new关键字进行调用，为了创建一个自定义的类，并且创建这个类的实例。
实例:是类实例化之后一个一个具体的对象。
原型：通过现有实例来生成新实例的函数，也是一个对象。
原型链：就是联系实例与原型的链条。

# # # # # # # # # # # # # # # # # # # # # # # # # # 创建对象
## 利用 new Object() 创建对象
var obj1 = new Object();

## 利用 对象字面量创建对象
  var obj2 = {};

## 利用构造函数创建对象
function Star(){
 //some code
}
let a = new Star()

new在执行中会做四件事
（1）在内存中创建一个新对象
（2）让this指向这个新对象
（3）执行构造函数里面的代码，给这个新对象添加属性和方法
（4）返回这个新对象（返回构造函数里面不需要return)

# # # # # # # # # # # # # # # # # # # # # # # # # #  构造函数
## 每个构造函数都有一个prototype属性，指向另一个对象。
## 每个对象都有一个__proto__  属性指向 它的构造函数的prototype
a.__proto__ == Star.prototype                    (Star.prototype.constructor == Star)
Star.prototype.__proto__ == Object.prototype
Object.prototype.__proto__ == null
