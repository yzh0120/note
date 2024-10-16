new Promise((resolve, reject)=>{
    //做一些异步操作
		setTimeout(function(){
			console.log('执行完成Promise');
			resolve('要返回的数据可以任何数据例如接口返回数据');
		}, 2000);
})


## Promise.all()方法用于将多个 Promise 实例，包装成一个新的 Promise 实例。
Promise.all([
    // 等数据中的所有接口都执行resolve()成功状态后，执行then()方法。
    pro1,
    pro2,
    pro3,
]).then((resList) =>{
    // 最终以数组的形式返回，数据顺序，和all()中的数据顺序一致。
    console.log('resList--', resList);
}).catch(error =>{
    // 上述接口中有一个接口返回reject()失败状态，就不走then()方法，走catch方法。
    // 任务中只要有接口报错，就会返回最先报错接口的reject()数据，其他接口可继续执行，但不会走then()方法。
    console.log('error--', error);
})

## Promise.race()方法同样是将多个 Promise 实例，包装成一个新的 Promise 实例。
const p = Promise.race([p1, p2, p3]);
p.then(data => {
                console.log(data)  //打印结果为data1
            })
						.catch(console.error);//如果返回reject 则执行catch
上面代码中，只要p1、p2、p3之中有一个实例率先改变状态，p的状态就跟着改变。那个率先改变的 Promise 实例的返回值，就传递给p的回调函数。

## PES2020 引入了Promise.allSettled()方法，用来确定一组异步操作是否都结束了（不管成功或失败）。所以，它的名字叫做”Settled“，包含了”fulfilled“和”rejected“两种情况。
## 该方法返回的新的 Promise 实例，一旦发生状态变更，状态总是fulfilled，不会变成rejected。状态变成fulfilled后，它的回调函数会接收到一个数组作为参数，该数组的每个成员对应前面数组的每个 Promise 对象。
await Promise.allSettled(promises);

## Promise.any()方法。只要参数实例有一个变成fulfilled状态，包装实例就会变成fulfilled状态；如果所有参数实例都变成rejected状态，包装实例就会变成rejected状态。
const promises = [
  fetch('/endpoint-a').then(() => 'a'),
  fetch('/endpoint-b').then(() => 'b'),
  fetch('/endpoint-c').then(() => 'c'),
];

try {
  const first = await Promise.any(promises);
  console.log(first);
} catch (error) {
  console.log(error);
}
