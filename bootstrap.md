[toc]
# BootStrap
[bootstrap中文网](https://www.bootcss.com/)
## 一.响应式布局(css3 2010年提出)
### 1.什么是响应式网页
```
Responsive web  page 响应式/自适应网页
可以根据浏览设备不同(pc,pad,phone)而自动改变布局,图片,文本效果,不会影响用户体验
```
### 2.响应式布局必须保证几件事
```
布局,尽量不使用固定值宽度,必须是流式布局(默认文档流+浮动)+弹性
文字和图片大小随着容器大小改变(% rem)
使用css3提供的媒体查询技术

注意:代码复杂的页面,不适合使用响应式布局
```

### 3.测试响应式网页的方式
```
1. 使用真实设备
    好处:真实可靠
    坏处:成本高,测试任务量巨大
2. 使用第三测试软件
    好处:不需要成本,测试方便
    坏处:测试效果有限,需要进一步验证
3. 学习过程,使用chrome自带的模拟软件
    好处:方便,简单
    坏处:测试效果十分有限
```
### 4.编写响应式网页( **重点** )
#### 4.1. 移动端适配(移动端运行,一定要写)
```
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">
width=device-width 视口宽度为设备宽度
initial-scale=1.0,   设置视口初始缩放为1倍,不放大不缩小
maximum-scale=1.0,   允许视口最大放大到1倍
user-scalable=0      是否允许用户缩放视口 0,不允许
简洁的写法
<meta name="viewport" content="width=device-width, initial-scale=1">
```
#### 4.2. 所有的内容/文字/图片尽量使用相对尺寸,不使用绝对值
#### 4.3. 流式布局+弹性布局+媒体查询,完成响应式布局
#### 4.4. 媒体查询 CSS3 Media Query,做响应式必备的技术
```
Media 媒体,浏览网页的设备
设备的分类: screen (pc/pad/phone)
            TV
            print
Media Query:根据当前浏览页面的设备不同(尺寸,硬件,方向,解析度),有选择则性的,执行一部分css,忽略掉其它css样式
语法 @media sreen and 尺寸{ 样式 }
尺寸:w>=1200 xl 超大
     992<=w<=1199  lg 大屏
     768<=w<=991   md 中屏幕
     576<=w<=767   sm 小屏
     <=575         xs 超小
```
---

## 二.BootStrap
```
起步,如何使用boot
全局css样式
组件 +js 插件
定制 sass
boot 项目
```
---

### 1.如何使用boot
```
按照顺序导入4个文件
<link rel="stylesheet" href="./css/bootstrap.css">
<script src="./js/jquery.min.js"></script>
<script src="./js/popper.min.js"></script>
<script src="./js/bootstrap.min.js"></script>
body中添加容器div.container
所有boot代码写在容器中
boot只支持4个屏幕,没有xs
boot中rem=16px
```

### 2.全局css样式
```
.container 定宽容器,每种不同分辨率下,给了写死的max-width
.container-fluid变宽容器,宽度永远是父元素的100%
```
#### 2.1.按钮
```
btn 基本类.
按钮颜色
btn-danger 红色
btn-success 绿色
btn-warning 黄色
btn-primary 主要的 蓝色
btn-secondary 次要的 灰色
btn-info  信息 藏青色
btn-dark 深色
btn-light 浅色
只有边框的按钮
btn-outline-info/danger/.......
不同按钮大小
btn-lg
btn-sm
btn-block
btn-link
```
#### 2.2.图片相关
```
rounded 圆角4px
rounded-circle 圆角50%
img-thumbnail 缩略图,有内边距有边框的图片
img-fluid 响应式图片,图片可以缩放,但是最大不能超过原始尺寸
```
#### 2.3.文字相关
```
text-danger/info/warning..... 字体颜色
text-muted 灰色字体
text-capitalize 首字母大写
text-uppercase/lowercase 大小写
font-weight-light/normal/bold
字号 h1~h6 类名
文本对齐,封装媒体查询
text-*-left/right/center  *:xl/lg/md/sm
text-justify没有封装媒体查询  
任务,自己手写媒体查询,封装
text-lg-justify text-md-justify text-sm-justify  
boot中封装的媒体查询有向上兼容的问题
sm  在sm/md/lg/xl下生效
md  在md/lg/xl下生效
lg  在lg/xl下生效
xl  在xl下生效
```
####  2.4.列表相关
```
list-unstyled 去点,清除左内边距
ul.list-group>li.list-group-item 创建列表组和列表项
列表项颜色
li.list-group-item-danger/warning......
激活/禁用项
active/disabled
```
####  2.5.表格相关
```
table 基本类,对表格和后代进行布局
table-bordered 为表格和后代添加边框
table-info/danger... 为表格添加颜色
table-striped        隔行变色
table-hover          鼠标悬停变色
``` 
### 3.辅助类  
#### 3.1.边框
``` 
border   基本类,设置4个方向边框
border-top/right/bottom/left      基本类,设置一个方向的边框
border-0  清除边框
border-top/right/bottom/left-0 清除一个方向的边框
border-danger.....  边框颜色
```
#### 3.2.浮动
```
float-*-left/right/none *:xl/lg/md/sm
```    
#### 3.3.背景
```  
bg-danger/info...
```
#### 3.4.显示
```    
visible 显示
invisible 隐藏
``` 
#### 3.5.内外边距
```
m/mt/mr/mb/ml/mx/my-*-0/1/2/3/4/5/auto
*:xl/lg/md/sm
p/pt/pr/pb/pl/px/py-*-0/1/2/3/4/5
*:xl/lg/md/sm   padding没有auto
0:0rem
1:0.25rem
2:0.5rem
3:1rem
4:1.5rem
5:3rem
```
#### 3.6.尺寸
```
w-25/50/75/100
mw-100 max-width:100%
h-25/50/75/100
mh-100 max-height:100%
```
#### 3.7.圆角
```    
rounded/rounded-0 圆角0.25/去除圆角
rounded-top/right/bottom/left
```
### 3.栅格布局
table布局 | div+css布局 | boot中的栅格
---|---|---
|简单,容易控制 |语义正确,渲染效率高 | 简单,容易控制,语义正确,渲染效率高,支持响应式
语义错误,渲染效率低| 控制起来比较麻烦,手写媒体查询| 复杂页面不适用

#### 3.1.使用栅格,容易控制
```
.row>col-1/2/3/4/5/6/7/8/9/10/11/12
```
#### 3.2.响应式栅格
```
.row>col-*-1/2/3/4/5/6/7/8/9/10/11/12
*:xl/lg/md/sm
```
#### 3.3.使用栅格的注意事项
```
row:弹性,主轴横向,可换行,左右自带-15px外边距(清0)
col:左右自带15px内边距(清0)
no-gutters 写在row的div,把row的mx-0,把col的px-0
```
#### 3.4.boot的响应式向上兼容
```

```
#### 3.5.col
```
.col 让内部元素平局分配空间,甚至可以大于12个
```
#### 3.6.列偏移
```
offset-1/2/3/4/5/6/7/8/9/10/11 底层是margin-left
```
#### 3.7.栅格嵌套
```
.row直接子元素只能是col
需要在col中,再写.row>.col
```
### 4.boot响应式向上兼容的问题
```

```

### 5.弹性布局
```
d-*-flex/none/block/inline/inline-block/table
*-xl/lg/md/sm
所有弹性,主轴为x轴(换行),都可以替代栅格的.row
1.主轴方向
flex-*-row/row-reverse/column/column-reverse *:xl/lg/md/sm
2.主轴对齐方向
justify-content-*-around/between/start/center/end *:xl/lg/md/sm
```
### 6.表单
#### 6.1.表单元素的排列方向
```
form-group堆叠表单,垂直方向排列
form-inline 内联表单,水平方向排列(弹性布局,主轴x轴)
```
#### 6.2.表单元素的样式
```
对文本框的设置
form-control 文本框的基本类 块级 w-100 边框 圆角 过渡 focus
col-form-label/-lg/-sm 设置文本到边框的距离
对checkbox的布局
父级.form-check 相对定位
<input checkbox> .form-check-input 绝对定位
.form-text 块级,上外边距4px
```
## 三.组件
```
页面中一些特殊的效果,被 boot 封装了,让我们更方便,更快捷的写出页面效果
boot组件事件,是通过自定义属性和值来调用的
1.在调用事件的元素上==
2.事件发生之后,事件目标 
```

### 1.下拉菜单
```
基本结构
div.dropdown             相对定位
>button.dropdown-toggle  画三角
+ul.dropdown-menu        绝对定位,d-none
事件 button添加自定义属性 data-toggle="dropdown"
     不需要写事件目标
```
## 四.定制scss(sass)
```

```

  
 
  




  