## var let const 声明变量的方式以及不同

1. let const 声明的变量只在其所在的代码块内有效（同一个{}）内。
2. var 在for循环中经常有变量i在循环外别访问到的情况，使用let不会出现
3. var 会存在变量提升。使用let 在未经声明之前使用以及赋值会报错(暂时性死区)。
4. let 在相同作用域内不能重复声明。
5. const 用来声明一个只读的常量，不可修改
6. 通过var声明的全局变量会自动挂载在全局对象（window 或者 global）上，使用let const 不会有这种情况。



### 变量提升

  简单介绍就是 在一个变量声明之前，使用了改变量，该变量为undefined。
  ~~~(javascriipt)
   var a = 1234;
   function test() {
      console.log(a)
      var a = 1111
   }
   
   // a变量提升 输出 undefined
  ~~~
