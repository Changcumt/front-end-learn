## async await

参考文章：
   * http://es6.ruanyifeng.com/#docs/async 

该函数本质是 Generator 函数的语法糖。

优点：

* 避免回调函数地狱
* 避免Promise的.then函数过多导致的代码冗余
* 比Generator有更好的语义，更广泛的适用性，并且返回的是 Promise

注意点：
* async函数返回一个 Promise 对象，可以使用then方法添加回调函数。当函数执行的时候，一旦遇到await就会先返回，等到异步操作完成，再接着执行函数体内后面的语句。
* async函数内部return语句返回的值，会成为then方法回调函数的参数。
* async函数内部抛出错误，会导致返回的 Promise 对象变为reject状态。抛出的错误对象会被catch方法回调函数接收到。
* async函数返回的 Promise 对象，必须等到内部所有await命令后面的 Promise 对象执行完，才会发生状态改变，除非遇到return语句或者抛出错误。
* await命令后面是一个 Promise 对象。如果不是，会被转成一个立即resolve的 Promise 对象。
* await命令后面的 Promise 对象如果变为reject状态，则reject的参数会被catch方法的回调函数接收到。
* 多个await命令后面的异步操作，如果不存在继发关系，最好让它们同时触发。封装成 Promise.all([])
* await命令只能用在async函数之中，如果用在普通函数，就会报错
