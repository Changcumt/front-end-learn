## @规则

参考文档

https://developer.mozilla.org/zh-CN/docs/Web/CSS/At-rule

### @charset 设置样式表字符编码

  如果设置，必须是样式表中第一个元素。该规则主要是针对使用非ASCII字符时候有用，比如content
  
  ~~~
  @chartset "UTF-8";
  ~~~

### @import 引入外部样式表

    @import 规则必须先于其他规则，除了@charset
    @import [ <string> | <url> ] [ <media-query-list> ]?;
    
  ~~~
  @import url("fineprint.css") print;
  @import url("bluish.css") projection, tv;
  @import 'custom.css';
  @import url("chrome://communicator/skin/");
  @import "common.css" screen, projection;
  @import url('landscape.css') screen and (orientation:landscape);
  ~~~

### @namespace 指定命名空间
    针对XHTML 以及svg等有XML命名空间的元素，把样式限定在这些元素之内
  ~~~
    @namespace url(http://www.w3.org/1999/xhtml);
    @namespace svg url(http://www.w3.org/2000/svg);

    /* 匹配所有的XHTML <a> 元素, 因为 XHTML 是默认无前缀命名空间 */
    a {}

    /* 匹配所有的 SVG <a> 元素 */
    svg|a {}

    /* 匹配 XHTML 和 SVG <a> 元素 */
    *|a {}
    
  ~~~

### @media 媒体查询
  
  @media 媒体类型 and 媒体特性 {}
  
  媒体类型有 all print screen speech
  
  媒体特性：
  
   name | summary | notes
   -- | -- | --
  width/min-width/max-width | 可视宽度 | 
  height/min-height/max-heihgt | 可视高度 |
  aspect-ratio/min-aspect-ratio/max-aspect-ratio |可见区域宽高比|   (min-aspect-ratio: 8/5)
  orientation | 可见区域高度是否大于或等于宽度 | portrait:高度大于宽度  landscape：宽度大于高度
   





