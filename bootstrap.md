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
min-width:向上
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
min-width:向上
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

    页面中一些特殊的效果,被 boot 封装了,让我们更方便,更快捷的写出页面效果
    == boot组件事件,是通过自定义属性和值来调用的
    == 1.在调用事件的元素上==
    == 2.事件发生之后,事件目标 


### 1.下拉菜单
```
基本结构
div.dropdown             相对定位
>button.dropdown-toggle  画三角
+ul.dropdown-menu        绝对定位,d-none
事件 button添加自定义属性 data-toggle="dropdown"
     不需要写事件目标
```
### 2.按钮组
```
div.btn-group-vertical 垂直按钮 .btn-group 水平按钮
>btn
btn-group-sm/lg 小/大按钮
```
### 3.信息提示框
```
结构
div.alert alert-danger/warning... alert-dismissible>span.close  与父元素alert-dismissible配合,给小叉叉样式
事件
span data-dismiss="alert"
```
### 4.导航
#### 4.1.水平导航
```
ul.nav  弹性/x轴/wrap 可以设置nav-justified
>li>nav-item 与父元素nav-justified配合,让每一项等宽显示
>a.nav-link 块级,hover去下划线
```
#### 4.2.选项卡导航
```
结构
 上部分,选项卡部分
ul.nav .nav-tabs 设置了边框
>li.nav-item     
>a.nav-link      设置了hover的边框  .active 选中状态
 下部分,内容
div.tab-content
>div.tab-pane    .tab-content .tab-pane 隐藏
                 .active 显示
```
#### 4.3.胶囊导航
```
ul.nav.nav-pills
a data-toggle="pill"
```
### 5.响应式导航栏
```
div.navbar  .navbar-expand-xl/lg/md/sm
>ul.navbar-nav 弹性,默认y轴
>li.nav-item
>a.nav-link
注意: div.navbar-expand-* 与子元素 ul.navbar-nav 配合组成一个选择器
        当父元素类名成立,子元素的主轴为row
        当父元素类名不成立,子元素的主轴为column
      形成了响应式的导航栏
```
### 6.折叠效果
```
结构
button
+div.collapse  隐藏
事件
button data-toggle="collapse" data-target="#id"
```
### 7.卡片
```
div.card
>div.card-header
+div.card-body
+div.card-footer
```
### 8.手风琴效果
```
<h3>手风琴</h3>
<div id="parent">
    <div class="card">
        <div class="card-header">
            <a data-toggle="collapse" class="card-link" href="#c1">卡片1</a>
        </div>
        <div data-parent="#parent" id="c1" class="collapse">
            <div  class="card-body ">
                卡片1 lorem20
            </div>
        </div>
    </div>
    <div class="card">
        <div class="card-header">
            <a data-toggle="collapse" class="card-link" href="#c2">卡片2</a>
        </div>
        <div data-parent="#parent" id="c2" class="collapse">
            <div  class="card-body ">
                卡片2 lorem20
            </div>
        </div>
    </div>
    <div class="card">
        <div class="card-header">
            <a data-toggle="collapse" class="card-link" href="#c3">卡片3</a>
        </div>
        <div data-parent="#parent" id="c3" class="collapse">
            <div  class="card-body ">
                卡片3 lorem20
            </div>
        </div>
    </div>
</div>
注意事项
1. .card-body和.collapse 不能作用在同一个div上,不然会卡顿
  解决方案 div.collapse>div.card-body
2.几个被折叠的部分,可以同时打开,而不是只能打开一个
  解决方案:在所有card外面,添加父元素div#parent
           在所有的div.collapse中添加自定义属性
           data-parent="#parent"

```
### 9.折叠导航栏
```
结构
div.navbar       导航栏标准类
   .navbar-dark  告诉孩子们,导航栏背景是深色,你们用浅色的文字控制了button的颜色,ul的文本颜色
   .bg-dark      背景为深色
   .navbar-expand-* 让按钮在*以上的屏幕,隐藏
                    让导航在*以上横向显示
>a.navbar-brand  不折叠的菜单项
+button.navbar-toggler 改变按钮背景色
 >span.navbar-toggler-icon 按钮中间3条线
+div.collapse 隐藏
    .navbar-collapse 调整隐藏菜单的显示位置
    >ul.navbar-nav>li.nav-item>a.nav-link
```
```
<div class="container">
    <div class="navbar bg-dark navbar-dark navbar-expand-md">
        <!-- 1.不折叠的菜单项-->
        <a class="navbar-brand" href="">Bootstrap中文网</a>
        <!-- 2.按钮,小屏显示,大屏隐藏-->
        <button data-toggle="collapse" data-target="#content" class="navbar-toggler">
            <span class="navbar-toggler-icon"></span>
        </button>
        <!-- 3.隐藏的菜单,大屏横向显示,小屏隐藏,纵向显示-->
        <div id="content" class="collapse navbar-collapse">
            <ul class="navbar-nav">
                <li class="nav-item">
                    <a href="" class="nav-link">boot3</a>
                </li>
                <li class="nav-item">
                    <a href="" class="nav-link">boot4</a>
                </li>
                <li class="nav-item">
                    <a href="" class="nav-link">Scss</a>
                </li>
                <li class="nav-item">
                    <a href="" class="nav-link">jQuery教程</a>
                </li>
                <li class="nav-item">
                    <a href="" class="nav-link">网站实例</a>
                </li>
            </ul>
        </div>
    </div>
</div>
```

### 10.媒体对象
```
div.media
>img
+div.media-body
```
### 11.焦点轮播图
```
1.轮播图片
div.carousel                相对定位
 >div.carousel-inner        w100 溢出隐藏
  >div.carousel-item.active    display:none
   >img.w-100
事件
在最外层div中 data-ride="carousel"

2.左右箭头
a.carousel-control-prev/next
 >span.carousel-control-prev/next-icon
我们需要重写样式
.carousel-control-prev,
.carousel-control-next{
    width: 4%;
    height: 20%;
    background: #aaa;
    top: 40%;
    border-radius: 0.25rem;
事件
a data-slide="prev/next" href="#最外层div的id"

3.轮播指示器
ul.carousel-indicators 弹性,x轴
 >li        重写li的样式  .active
.carousel-indicators li{
    width:0.8rem;height:0.8rem;
    background-color:#fff;
    border-radius: 50%;
    margin-left: 0.4rem;
    margin-right: 0.4rem;
}
.carousel-indicators .active{
    background-color:#0aa1ed;
}
事件
li data-target="#demo" data-slide-to="0"图片的下标,从0开始
```
### 12.模态框
```
<div class="modal">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header"></div>
      <div class="modal-body"></div>
      <div class="modal-footer"></div>
   </div>
  </div>
</div>
```
---

## 四.其它组件
### 1.徽章
```
badge 基本类
badge-danger/warning...
badge-pill  胶囊徽章
```
### 2.巨幕
```
jumbotron 巨大的内边距和背景色
```
### 3.分页条
```
ul.pageination
 >li.page-item .acttive/.disabled 选中/禁用
  >a.page-link
```
### 4.面包屑导航
```
ul.breadcrumb
 >li.breadcrumb-item
  >a
重写样式,改变连接符号
.breadcrumb-item + .breadcrumb-item::before{
        content: ">";
    }
```
### 5.进度条
```
div. progress       进度条的槽
 >div. progress-bar 进度条
使用bg-danger/...   控制颜色
   使用w-75 控制进度
.progress-bar-animated  带动画的进度条
.progress-bar-striped   带斜线的进度条
```
---

## 五.boot的定制

```
boot最重要的,媒体查询+栅格布局+scss
```

### 1.css的缺点
```
语法不够强大,没有变量和合理的样式复用机制,导致难以维护
使用动态样式语言,赋予css新的特性,提高样式的可重用性和可维护性
常用的动态样式语言
1.scss/sass(scss兼容sass,scss更贴近css的语法)
2.less
3.stylus
```
### 2.scss是什么
```
scss 是一款强大的css辅助工具
它和css的语法十分相似,在css的基础上添加了变量,嵌套,混合,导入,函数等高级功能
这些拓展命令,让css更加的强大与优雅
```

### 3.scss的使用

```
运行在服务器
把.scss文件转换成.css文件
传递给前端,让浏览器运行
浏览器本身不具备运行.scss的能力  
需求,node 版本8.11(10.01)
1.使用无网络的安装方式 
2.在线安装
cmd中 npm install -g node-sass
node-sass -v验证
```
### 4.scss文件转换成css文件
```
1.单文件转换
node-sass  scss文件路径  css文件路径
ex:node-sass scss/01.scss css/01.css
2.批量转换,一次转一个文件夹
node-sass scss文件夹 -o  css文件夹
node-sass scss -o css
3.单文件监听
node-sass -w 要监听的scss文件  要转换成的css文件
node-sass -w scss/01.scss css/01.css
4.多文件监听
node-sass -w scss文件夹 -o css文件夹
ex: node-sass -w scss -o css  
```

## 六.scss基础语法
### 1.变量
```
$jd_red:#f10215;
使用$声明变量,变量名可以包含-_,命名规则基本上与选择器规则相同
尽量做到见名知意
1.声明变量时,变量值可以引用其他变量
2.变量存在作用域,在{}外不能用
3.重复的变量声明,后声明会覆盖之前的声明的变量
!default规则,如果一个变量声明了!default.
这变量之前被声明过,就使用之前值
这个变量没有被声明过,就使用现在的值
```
### 2.嵌套
```
结构的嵌套
伪类嵌套,需要占位符&.不然会有空格
a{
  color:#fff;
  &:hover{color:#f00;}
}
群组的嵌套
属性嵌套(违反css编码原则)
  border:{style:solid;width:10px;color:#ff0;};
```

### 3.导入

```
在scss语法中,如果一个scss文件以_开头,那么这个文件就是一个局部scss文件,局部scss文件是不会转换成css文件的
需要在全部文件中导入局部文件,再把全部文件转换成css文件
_abc.scss
导入语法 @import"abc";
局部文件被导入后.局部文件中的代码会在全局文件中生成
局部文件的变量可以在全局文件
```
### 4.混合器

```
把一段经常被使用的样式封装成混合器
哪里需要使用,就调用混合器,实现代码的重用
定义混合器
@mixin 混合器名称(参数1,参数2){样式}
调用混合器 @include 混合器名称(实参1,实参2);
```

### 5.继承

```
一个选择器可以继承另外一个选择器所有的样式
@extend 选择器名称;
继承效果,两个选择器,形成群组选择器
```


### 6.运算
> 相对单位不能转换,绝对单位可以自动转换
#### 6.1加法

```
字符串拼接的时候
如果使用带双引号的字符串+不带双引号的字符串,结果带双引号
如果使用不带双引号的字符串+带双引号的字符串,结果不带双引号
```
#### 6.2减法

```
由于变量声明的时候,可以使用-
系统分不清楚,- 是变量名称还是减法
我们写的时候在-前后添加空格.告诉系统,我是减号
width:$my-width - $my-width1;
```

#### 6.3除法
```
scss中 /,除了解析成除法外,还被看成分割符
视为除法的几种情况
1.如果运算式两边的数字,是变量或者方法的返回值
2.运算式被()包裹
3.除法运算式,是其它运算式的一部分
```
#### 6.4.scss字符串中的插值操作

```
content:"liangCheng ate #{50+100} baozis";
```

#### 6.5.颜色的计算

```
分段计算    r+r  g+g  b+b 如果超过255,或者ff.就取ff或者255
rgb(11,22,33)+#162c42
rgba的计算,需要a的值,相同,才可以计算
```
### 7.函数

#### 7.1.scss中定义了很多函数,有些函数直接在css中使用

```
rgba
hsl(hue,saturation,lightness)
hue:色调  0~360
saturation:饱和度  0.0%~100%
lightness:亮度 0.0%~100%
background:hsl(120,100%,50%); 

```
#### 7.2.数学函数

```
round($val) 四舍五入
ceil($val)  向上取整
floor($val) 向下取整
min($v1,$v2...)
max($v1,$v2...)
random()     随机数
```

#### 7.3.字符串函数

```
unquote($str) $str去掉引号
quote($str) $str加上引号
to_upper_case($str) $str转成大写
to_lower_case($str) $str转成小写
```

#### 7.4.自定义函数

```
@function 方法名称($v1,$v2....){
  逻辑
  @return 返回值;
}
```

### 8.指令

```
@if(){
}@else if(){
}@else{}
```


