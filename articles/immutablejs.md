### immutable.js
immutable.js 可以提高React的性能。为什么可以提高React的性能，需要先了解React的渲染机制以及更新dom的过程，了解Comment和PureComment的区别。
使用Component,setState或者props更新的时候，本组件下的所有子组件都会检测所绑定的值是否有变动，如果有变动，则更新dom。 PureComment则是只会在
浅层次的比较，如果数据没有发生变化，则不会继续深入到子组件去对比。所以使用immutable经常要配合PureComponent来使用。（tip:复习React文档）

[文档](https://immutable-js.github.io/immutable-js/docs/#/List)

#### 常用类型

1. List, 类似于Javascript的Array
```
import {List} from 'immutable
// 声明一个List,传入一个类集合的对象

const numberList = List([1,2,3,4])  // List[1,2,3,4]
const setList = List(Set[1,2,3,3]) // List[1,2,3]

// 判断是否是List
List.isList(setList)  //true

// 集合大小
numberList.size // 4

// 修改值 set(index,value)
numberList.set(1,5555) // List[1,5555,3,4]

// 取值

numberList.get(1) // 2
```

此外，还有pop,push,shift,unshift,map,some,every等Array的方法，还有toJS() toJSON() toArray() 等

2. Map 类似于Javascript中的Object

```
// 声明一个Map
const myMap = Map({a:1})

// 修改
myMap.set('a',1234) // Map {"a":1234}

// 深层次修改
const deepMap = Map({a:{b:{c:'haha'}}})
deepMap.setIn(['a','b','c'],"Ha Ha!")

```

3. OrderedMap 有顺序的map,顺序是key指定的先后顺序

4. Set 类似javascript中的Set

5. Record, 类似Object, 可以扩展 以及设置属性默认值

```
const { Record } = require('immutable')
const ABRecord = Record({ a: 1, b: 2 })
const myRecord = ABRecord({ b: 3 })
```

6. Seq 高效的对集合链式操作的一种结构

```
const { Seq } = require('immutable')
const oddSquares = Seq([ 1, 2, 3, 4, 5, 6, 7, 8 ])
  .filter(x => x % 2 !== 0)
  .map(x => x * x)
  
```

此外还有就是Object 常用的方法

#### 常用方法
1. fromJs() 默认将Object转成Map 数组转成List
2. getIn 类似dotProp

```
const { getIn } = require('immutable')
getIn({ x: { y: { z: 123 }}}, ['x', 'y', 'z']) // 123
getIn({ x: { y: { z: 123 }}}, ['x', 'q', 'p'], 'ifNotSet') // 'ifNotSet'

```

#### React中常用模式

#### 与Redux结合使用


