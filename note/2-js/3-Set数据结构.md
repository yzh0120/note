## 它类似于数组，但是成员的值都是唯一的，没有重复的值。
## 所以 // 去除数组的重复成员
[...new Set(array)]

## 生成set
const set = new Set([1, 2, 3, 4, 4]);
# # # # # # # # # # # # # # # # # # # # # # # # # # # 属性
## Set.prototype.size：返回Set实例的成员总数。

# # # # # # # # # # # # # # # # # # # # # # # # # # # 方法

## Set.prototype.add(value)：添加某个值，返回 Set 结构本身。
## Set.prototype.delete(value)：删除某个值，返回一个布尔值，表示删除是否成功。
## Set.prototype.has(value)：返回一个布尔值，表示该值是否为Set的成员。
## Set.prototype.clear()：清除所有成员，没有返回值。



# # # # # # # # # # # # # # # # # # # # # # # # # # #Set 结构的实例有四个遍历方法，可以用于遍历成员。

## Set.prototype.keys()：返回键名的遍历器
## Set.prototype.values()：返回键值的遍历器
## Set.prototype.entries()：返回键值对的遍历器
## Set.prototype.forEach()：使用回调函数遍历每个成员
