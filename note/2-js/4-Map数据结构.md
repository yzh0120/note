# # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # map结构的“键”的范围不限于字符串,是一种更完善的 Hash 结构实现
const m = new Map();
const o = {p: 'Hello World'};
m.set(o, 'content')

# # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # #属性
## size 属性返回 Map 结构的成员总数。
const map = new Map();
map.set('foo', true);
map.set('bar', false);
map.size // 2

# # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # #方法
## Map.prototype.set(key, value) set方法设置键名key对应的键值为value，然后返回整个 Map 结构。如果key已经有值，则键值会被更新，否则就新生成该键。
set方法返回的是当前的Map对象，因此可以采用链式写法。
let map = new Map()
  .set(1, 'a')
  .set(2, 'b')
  .set(3, 'c');

## Map.prototype.get(key) get方法读取key对应的键值，如果找不到key，返回undefined。

## Map.prototype.has(key) has方法返回一个布尔值，表示某个键是否在当前 Map 对象之中。

## Map.prototype.delete(key) delete()方法删除某个键，返回true。如果删除失败，返回false。

## Map.prototype.clear() clear()方法清除所有成员，没有返回值。
