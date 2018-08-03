## 常用meta标签整理

> meta标签提供关于HTML文档的元数据。元数据不会显示在页面上，但是对于机器是可读的。它可用于浏览器（如何显示内容或重新加载页面），搜索引擎（关键词），或其他 web 服务。 —— W3School

属性 | 值 | 描述
--   | -- | --
http-equiv | content-type/expire/refresh/set-cookie |
name | author/keywords/description/generator/revised/... | 
content | some text | 针对http-equiv 和 name的值 |

### seo 用到的属性
eg.
  ```
  <meta name=-"keywords" content="tag1.tag1">
  ```
  * keywords:页面关键词。 标记不能超过874个字符
  * description:页面描述。 不超过150字符
  * robots:搜索引擎搜索方式（all：文件将被检索，并且链接可被检索；node:文件不会被检索，链接不可以被检索；index：文件可以检索；follow：链接可以被查询；noindex:文件将不被检索；nofollow:页面上的链接不可以被查询）
  * author：网页作者
 
### 移动设备
  * viewport: 定义视图属性（width:宽度（数值200-10000，device-width,默认为屏幕物理像素），height（数值23-10000，device-height），initial-scale：初始缩放比例0-10，minimum-scale：最小缩放比例,maximum-scale:最大缩放比例，user-scalable：用户是否可以手动缩放（no,yes））
  * apple-mobile-web-app-capable:app全屏模式（content为 yes）
  * apple-mobile-web-app-status-bar-style:开启webapp模式后设置状态栏页面（default,black,black-translucent）
  * apple-mobile-web-app-title:webapp添加到屏幕后的标题
  * format-detection:ios 识别设置（telephone=no 忽略识别电话号码，email=no 忽略识别邮箱）
  * apple-itunes-app 智能引导下载APP的广告
  
### 网页相关
  ```(html)
  <meta charset="utf-8">
  
  <meta http-equiv="X-UA-Compatible" content="IE-edge，chrome=1"> 
  //使用最新版本的IE内核 chrome内核
  
  <meta name="renderer" content="webkit|ie-comp|ie-stand">
  // 针对国内双核浏览器选择一种内核渲染
  
  <meta http-equiv="Pragma" content="no-catch">
  // 禁止浏览器从本地缓存访问页面，这样可以防止脱机浏览
  
  <meta http-equiv="expires" content="Wed, 26 Feb 1997 08:21:57 GMT">
  //设置缓存过期时间，一旦过期，则服务器需要重新请求数据
  
  <meta http-equiv="refresh" content="5;url=http://www.baidu.com">
  //5秒钟后自动跳转到百度页面，如果不指定url 则是自动刷新页面

  ```
