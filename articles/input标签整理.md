### input type可设置的类型有：
* button 按钮类型（已不推荐使用，使用<button>代替）

* checkbox 选择框

* file 文件

    可以设置的属性有accept,multiple,指定可上传文件类型，如accept="image/gif, image/jpeg" 或者 accept="image/*" 或者 accept="*.doc,*.docx".
    multiple是否可以上传多个文件
    
* hidden 隐藏的文本域（不会再页面展示，但是form表单提交时候会提交）

* image 图片提交按钮(不常使用)

* password 密码域

* radio 单选框

* reset 重置按钮（不常使用）

* submit 提交按钮（点击后 form表单会提交）

* text 文本域

* email 邮件

* url 链接

* number 数字

    可以设置min max step 在pc端有效果，在移动端没有效果。 移动端ios强制使用数字键盘 
    ```(html)
        <input type="number"  pattern="[0-9]*">
    ```
    
* range 范围

    可以设置 min max step
    
* Date pickers (date, month, week, time, datetime, datetime-local) 日期

    在pc端均可使用，在移动端（ios） week datetime 不可用。date选择年月日，month选择年月 time选择时分（ios上可以指定上下午）
    
* search 与text一致 (不常使用)

* color 颜色 

    在移动端不可用
    
 ### 其他input属性整理
 * autocomplete 是否自动完成 autocomplete="on" autocomplete="off" 如果设置为on,则浏览器会记住改input上一次输入的值，再次输入的时候可以自动补全。
 * list 设置可选值 与datalist组合使用
 * required
 * pattern 规则匹配
 
 
在表单提交的时候 chrome会根据pattern以及type自动判断值的有效性，但是默认的UI的太丑，所以还是自己用js判断规则吧。
