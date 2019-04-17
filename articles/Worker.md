### Worker 

http://www.ruanyifeng.com/blog/2018/07/web-worker.html

#### demo

~~~
// 主线程
    let worker = new Worker('./worker.js?a='+Date.now())
    worker.postMessage({ method: 'start', params: { a: 1, b: 1 } })
    worker.addEventListener('message',e=>{
      console.log('main.data',e.data)
    })

// worker 

self.addEventListener('message',e=>{
  console.log('worker.data',e.data)
  self.postMessage('2222')
})
~~~

#### 知识点
1 同源限制
2 不能操作DOM
3 可以发送ajax和加载其他脚本 但是不能使用alert confirm
4 无法读取本地文件


#### API

* Worker.onerror：指定 error 事件的监听函数。
* Worker.onmessage：指定 message 事件的监听函数，发送过来的数据在Event.data属性中。
* Worker.onmessageerror：指定 messageerror 事件的监听函数。发送的数据无法序列化成字符串时，会触发这个事件。
* Worker.postMessage()：向 Worker 线程发送消息。
* Worker.terminate()：立即终止 Worker 线程。

* self.name： Worker 的名字。该属性只读，由构造函数指定。
* self.onmessage：指定message事件的监听函数。
* self.onmessageerror：指定 messageerror 事件的监听函数。发送的数据无法序列化成字符串时，会触发这个事件。
* self.close()：关闭 Worker 线程。
* self.postMessage()：向产生这个 Worker 线程发送消息。
* self.importScripts()：加载 JS 脚本。


#### 适用场景
  负担一些计算密集型或高延迟的任务，比如图像处理，服务器轮询等
