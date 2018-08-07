## Grid布局
参考文章
* https://www.w3.org/TR/css-grid-1/
* https://blog.csdn.net/ceshi986745/article/details/51733383

支持情况：目前主流浏览器均已经支持

### 简介
Grid是一个基于二维网格布局的系统，与之相对的Flex布局是一维的。 Grid和Flex混合使用，可以极大的方便实现布局效果，尤其是响应式布局。

### 主要概念
* 网格容器（Grid Container）
  当一个元素设置 display:grid 的时候，该元素就成为了一个网格容器。其直接子元素成了网格项
* 网格项(Grid Item)
* 网格线（Grid Line）
  网格项之间的空隙，并不是一个实际元素的存在，但是可以设置宽度，并且每条线都有一个序号（从上到下或者从左到右，从1开始）
* 网格轨道（Grid Track）
  网格线之间的轨道
* 网格单元格（Grid Cell）
  由相邻的两个列线和两个行线确定的一个区域。单元格和网格项并不一致，有时候网格项会跨越多个单元格
* 网格区域
  由四条网格线围成的一个区域
  
### 网格属性
1. display(应用在容器)
~~~(CSS)
  .container {
    display:grid;
 }
~~~
