## Promise

参考教程
* http://es6.ruanyifeng.com/#docs/promise

简介：Promise是一种异步编程的解决方案。

特点：
* 只有三种状态：pending（进行中），fulfilled(已成功)，rejected(已失败)，只有异步的操作结果可以改变状态。
* 状态一旦改变就不能再改变，只能由pending到 fulfilled 或者是pending到rejected。

缺点：
* 一旦创建 无法取消

使用：
~~~
new Promise((resolve,reject)=>{
  // resolve(value) 将状态改为fuifilled 并将结果传递出去
  // reject(value) 将状态改为rejected 并将结果传递出去
})
// promise 一旦创建就会立即执行。 如果Promise中是一个立即返回结果的promise，then方法中函数执行的效果类似
// setTimeout(func,0)
~~~

### Promise.prototype.then
~~~
(new Promise()).then(()=>{
  // 成功时候执行的函数
},()=>{
  // 失败时候执行的函数
})

// then 方法返回的是一个新的promise实例，因此.then链式的写法可以一直写下去
// 在 .then的回调函数中 return一个值 这个值会被作为当前promise的值传递出去
~~~

### Promise.prototype.catch 

代码错误以及自己自定义的错误，和reject的结果均可以被catch捕捉到。

### Promise.prototype.finally 

无论失败或是成功，最后都会执行的回调函数

### Promise.all

将多个promise传入Promise.all()方法，返回一个新的promise，等到所有的promise成功之后 ，这个新的promise才会成功。

### Promise.race

传入多个Promise实例到Promise.race()中，返回一个新的promise，这些实例中谁先改变状态，这个状态就会改变新的promise的状态。
