### immutable.js
immutable.js 可以提高React的性能。为什么可以提高React的性能，需要先了解React的渲染机制以及更新dom的过程，了解Comment和PureComment的区别。
使用Component,setState或者props更新的时候，本组件下的所有子组件都会检测所绑定的值是否有变动，如果有变动，则更新dom。 PureComment则是只会在
浅层次的比较，如果数据没有发生变化，则不会继续深入到子组件去对比。所以使用immutable经常要配合PureComponent来使用。（tip:复习React文档）

#### 常用类型

1. List, 类似于Javascript的Array
```
import {List} from 'immutable
// 声明一个List,传入一个类集合的对象

const numberList = List([1,2,3,4])  // List[1,2,3,4]
const setList = List(Set[1,2,3,3]) // List[1,2,3]

// 判断是否是List
List.isList(setList)  //true

```
Map

#### 常用方法

#### React中常用模式

#### 与Redux结合使用


