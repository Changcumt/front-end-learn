## Set Map

### Set 

Set 是es6新增的一种数据结构，类似于数组，只是数据是唯一的。

使用：
~~~
  let s1 = new Set()
  s1.add(1)
  s1.add(2)
  
  let s2 = new Set([1,2,3,3,3,3])
~~~

#### Set.prototype.size 

  返回成员的数量
  
####  数据操作方法

  * add() 新增成员
  
  * delete() 删除某成员
  
  * has() 是否存在某成员
  
  * clear()  清空成员
  
#### 遍历操作

  * keys() 返回键名的遍历器
  * values() 返回值的遍历器（keys values 返回的值一致）
  * entries() 返回键值对的遍历器
  * forEach() 
 
#### 数组去重
~~~
  [...(new Set([1,1,1,1,2,2,3,4]))]
  
  Array.from(new Set([1,1,1,2,2,3,4]))
~~~

### Map 

  一种新的存储键值对的数据结构，传统的Object虽然也是通过键值对来存储值，但是键必须是字符串，而Map中的键可以是任意类型。
  
  使用：
  ~~~
    let m = new Map()
    m.set('a',1234)
    m.get('a')
    
    let m2 = new Map([
        ['a',1234],
        ['b',5678]
    ])
  ~~~
  
  ### 属性 & 方法
    
    * size 返回成员的数量
    * set(key,value)
    * get(key)
    * has(key)
    * delte(key)
    * clear()
    * keys()
    * values()
    * entries()
    * forEach()
  
  
  
  
  
