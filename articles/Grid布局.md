## Grid布局
参考文章
* https://www.w3.org/TR/css-grid-1/
* https://blog.csdn.net/ceshi986745/article/details/51733383

支持情况：目前主流浏览器均已经支持

因为此布局在有图表示的时候会更好理解，所以初次学习推荐看上边的参考文章。本文仅作为复习使用。

### 简介
Grid是一个基于二维网格布局的系统，与之相对的Flex布局是一维的。 Grid和Flex混合使用，可以极大的方便实现布局效果，尤其是响应式布局。你只需要定义一个容器元素并设置display：grid，使用grid-template-columns 和 grid-template-rows属性设置网格的列与 行的大小，然后使用grid-column 和 grid-row属性将其子元素放入网格之中。

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
    display:grid | inline-grid; // grid 产生一个块级网格容器 inline-grid 产生一个内联网格元素 
 }
~~~

2. grid-template-rows & grid-template-columns （应用在容器）

利用空格分隔的值来定义网格的行和列。值的大小表示轨道的宽度（或者高度），并且他们之间的空格表示网格线。
~~~(CSS)
.container {
    grid-template-columns:50px auto 100px;
    grid-template-rows:100px 200px 50px;
}
// 以上例子表示将一个网格容器分成了3*3的九宫格，第一列宽度为50px 
// 第2列宽度自适应 第三列宽度为100px, 第一行高度为100px 第2行高度为200px 第3行高度为50px。 
// 网格容器内的网格项会默认按照从左到右，从上到下的顺序依次排列下来。 
// 如果数量超出9个，多出来的元素的宽度会继续受列宽度的限制，高度为自己默认高度

// 此外 还支持 subgrid 这个属性值。 如果该网格容器本身也是一个网格项，则该项可以继承父元素

// 支持单位 fr 如  grid-template-columns: 1fr 1fr 1fr 表示每列宽度为三分之一  
// grid-template-columns:1fr 50px 1fr 表示两边的宽度为总宽度=50px后的二分之一。

// 支持repeat(次数，重复项) 如  grid-template-columns: repeat(2,50px) 100px 
// 等同于  grid-template-columns:50px 50px 100px;

~~~
3. grid-template-areas (应用在容器) & grid-area (应用在网格项)

    使用grid-area属性定义网格区域名称，从而定义网格模板。网格区域重复的名称就会导致内容跨越这些单元格。句点表示一个空单元格。语法本身提供了一种可视化的网格结构。
  ~~~（CSS）
  .item-a{
    grid-area: header;
  }
  .item-b{
    grid-area: main;
  }
  .item-c{
    grid-area: sidebar;
  }
  .item-d{
    grid-area: footer;
  }
  .container{
    grid-template-columns: 50px 50px 50px 50px;
    grid-template-rows: auto;
    grid-template-areas: "header header header header"
                         "main main . sidebar"
                         "footer footer footer footer"
  }
  ~~~
  
  4. grid-column-gap & grid-row-gap & grid-gap (应用在容器)
  
    设置网格线的宽度。 grid-gap是简写形式，grid-gap： <grid-column-gap> <grid-row-gap>
  
  5. justify-items & align-items （应用容器）
  
    justify-items 设置在沿水平方向如何对其网格项内的内容。 align-items 设置水平方向如何对其网格项内的内容。 
    
    属性值：start end center stretch
   
  6. justify-content & align-content(应用在容器)
    
    当给网格项设置固定宽高，不足以撑满容器时候可以设置的排列属性。justify-content 应用在水平方向，align-content 应用在垂直方向。
    
    属性值： start end center space-around space-between space-evenly
    
    space-around 网格项与最边缘的宽度为 网格项之间宽度的一半
    space-between 网格项与最边缘没有间隙
    space-evenly 网格项与最边缘的宽度与网格项之间的宽度一样
    
  7. grid-auto-columns & grid-auto-rows(应用在容器)
  
    设置自动生成的网格大小
    
  8. grid-auto-flow（应用在容器）
  
    控制自动布局算法
    row | column | row dense | column dense
    
  9. grid（应用在容器）
  ~~~
  .container{
    grid: none | subgrid | <grid-template-rows> / <grid-template-columns> | <grid-auto-flow> [<grid-auto-rows> [/ <grid-auto-columns>]];
  }
  ~~~
  
  10. 
    
    



















