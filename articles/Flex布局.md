## Flex布局

参考网址：
  http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html
 
Flex布局即为弹性布局。 在弹性布局元素内，float clear vertical-align失去效果。

### 容器属性
* flex-direction   row | row-reverse | column | column-reverse
* flex-wrap  nowrap | wrap | wrap-reverse;
* flex-flow  <flex-direction> || <flex-wrap>;
* justify-content  flex-start | flex-end | center | space-between | space-around;
* align-items  flex-start | flex-end | center | baseline | stretch;
* align-content   flex-start | flex-end | center | space-between | space-around | stretch;

### 项目属性
* order
* flex-grow
* flex-shrink
* flex-basis  <length> | auto; /* default auto */
* flex  none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
* align-self  auto | flex-start | flex-end | center | baseline | stretch;
