IE6-bugs
========
（内容来自妙味课堂笔记）
注意: html文件夹中有对应bug重现的html页面

#### 1.
计算一定要精确 不要让内容的宽高超出我们设置的宽高
在IE6下，内容会撑开设置好的宽高

#### 2.
在IE6元素浮动，如果宽度需要内容撑开，就给里边的块元素都加浮动

#### 3.
在IE6，7下元素要通过浮动并在同一行，就给这行元素都加浮动

#### 4. 
P标签中不要嵌套块元素

#### 5.
IE6下最小高度问题
在IE6下元素的高度的小于19px的时候，会被当做19px来处理

解决办法:overflow:hidden;

#### 6. 
1px dotted 在IE6下不支持 ，因为精度计算的问题，会显示成虚线，2px或大于2px的dotted就可以正常显示  

解决办法:切背景平铺

#### 7.
标准浏览器 解决子元素margin传递到父元素的bug 

解决方法: 

1.加float  

2.overflow:hidden IE6下需要出发haslayout

在IE6下解决margin传递要触发haslayout
 
(如果有边框margin就不会传递到父元素上 
在IE6下父级有边框的时候，子元素的margin值消失
解决办法:触发父级的haslayout ）

#### 8.
IE6下双边距BUG
在IE6，块元素有浮动和和横向的margin值 ，横向的margin值会被放大成两倍

解决办法: display:inline;

#### 9.
基于上面的bug

如果有一排浮动元素：

margin-right 一行右侧第一个元素有双边距

margin-left 一行左侧第一个元素有双边距

#### 10.
在IE6，7下，li本身没浮动，但是li的内容有浮动，li下边就会产生一个间隙

解决办法:

1.给li加浮动

2.给li加vertical-align

#### 11.
在IE6，7下，li本身没浮动，但是li的内容有浮动，li下边就会产生一个间隙 4px

解决办法:

1.给li加浮动

2.给li加vertical-align
 
当IE6下最小高度问题，和 li的间隙问题共存的时候 给li加浮动

解决方法: 先解决最小高度 overflow:hidden; 在加float处理li间隙

#### 12.
当一行子元素占有的宽度之和和父级的宽度相差超过3px, 或者有不满行状态的时候,最后一行子元素的下margin在IE6下就会失效

#### 13.
在IE6下的文字溢出BUG     
子元素的宽度和父级的宽度相差小于3px的时候,两个浮动元素中间有注释或者内嵌元素

解决办法:用div把注释或者内嵌元素用div包起来 


#### 14.
当浮动元素和绝对定位元素是并列关系的时候，在IE6下绝对定位元素会消失

解决办法: 给定位元素外面包个div


#### 15.
在IE6，7下，子元素有相对定位的话，父级的overflow包不住子元素

解决办法: 给父级也加相对定位

#### 16.
在IE6下绝对定位元素的父级宽高是奇数的时候，元素的right值和bottom值会有1px的偏差

解决方法: 不要给父元素设置奇数宽高

#### 17.
IE6下 不支持fixed定位方法，

解决方法: 通过js定位的方式

#### 18.
IE6下就不要给tr和tbody同时加背景样式

#### 19.
在IE6，7下输入类型的表单控件上下各有1px的间隙

解决办法: 给input加浮动
 

#### 20.
在IE6，7下输入类型的表单控件加border:none;

解决办法: 重置input的背景

#### 21.
在IE6，7下输入类型的表单控件输入文字的时候，背景图片会跟着一块移动

解决办法: 把背景加给父级
 
#### 22.
IE6不支持png24图片

解决方法：

1.使用js （http://dillerdesign.com/experiment/DD_belatedPNG/DD_belatedPNG_0.0.8a.js）

2.使用filter

#### 23：
在IE6下 在important 后边在家一条同样的样式，会破坏掉important的作用，会按照默认的优先级顺序来走

#### 24:
IE6,7,8下，不加docType的话，页面盒模型出现怪异模式

#### 25:
childNodes 在标准浏览器中包含了文本（注意：换行会被解析成文本）和元素类型的节点，非标准的IE6,7,8下，只包含元素节点。

解决方法：

使用children属性替代childNodes， 只取元素节点

#### 26：
IE6,7,8不支持 firstElementChild, lastElementChild nextElementSibling and previousElementSibling

解决方法:

兼容写法 ofirst = ele.firstElementChild || firstChild, 但是这种写法会在下面情况下出问题
```html
<!--注意下面ul中有换行 上面的方法在标准浏览器会拿到文本节点-->
<ul>
</ul>
```
处理方法：

ele.children[0]



如果有新发现，请继续补充

参考资料：
http://w3help.org/zh-cn/causes/index.html

