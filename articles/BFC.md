## BFC 

>浮动元素和绝对定位元素，非块级盒子的块级容器（例如 inline-blocks, table-cells, 和 table-captions），
>以及overflow值不为“visiable”的块级盒子，都会为他们的内容创建新的BFC（块级格式上下文）。

创造一个BFC需要满足的条件：
  * float的值不是none。
  * position的值不是static或者relative。
  * display的值是inline-block、table-cell、flex、table-caption或者inline-flex
  * overflow的值不是visible
  

BFC 作用：

  * margin折叠问题
  
  * 包含浮动（浮动，绝对定位），父元素盒子高度塌陷问题 
  
  * 避免文字环绕
  
  * 避免多列布局 子元素被挤下来
