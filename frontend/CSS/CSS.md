# CSS定义
**层叠样式表**(Cascading Style Sheets),是一种样式表语言，用来描述HTML文档的呈现（美化内容）
书写位置：`title`标签下方添加`style`双标签，`style`标签里面书写CSS代码
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>初识CSS</title>
    <style>
        /* CSS代码 */
        /* 选择器 { CSS属性 } */
    </style>
</head>
<body>
    <p>体验CSS</p>
</body>
</html>
```
```html
<style>
    /* CSS代码 */
    /* 选择器 {CSS属性} */
    /* 属性名与属性值成对出现 --> 键值对 */
    p {
        /* 文字颜色 */
        color: brown;
        /* 字号 */
        font-size: 30px;
    }
</style>
```
# CSS引入方式
- 内部样式表：学习使用
  - CSS代码写在`style`标签里面
- 外部样式表：开发使用
  - CSS代码写在单独的CSS文件中(.css)
  - 在HTML使用`link`标签引入 : `<link rel="stylesheet" href="">`
  `rel`:关系，此处为样式表

$mycss.css$
```css
/* 这个文件放CSS代码 */
/* 选择器 {CSS属性} */
p {
    color: red;
}
```
```html
<title>初识CSS</title>
    <!-- 引入外部样式表 -->
    <link rel="stylesheet" href="mycss.css">
```
- 行内样式：配合JavaScript使用
  - CSS写在标签的`style`属性值里
```html
<body>
    <p>这是p标签</p>
    <!-- 行内, style="" -->
    <div style="color: red; font-size: 30px;">这是div标签</div>
</body>
```
# 选择器
作用：查找标签，设置样式
## 基础选择器
- 标签选择器
- 类选择器
- id选择器
- 通配符选择器
## 标签选择器
标签选择器：使用标签名作为选择器-->选中所有同名标签设置相同的样式（无法差异化同名标签的样式）
>例如:p{},h1{},div{},a{},img{}
```html
<style>
    /* 定义 */
    p {
        color: red;
    }
</style>
<!-- 所有p标签内的字都变红 -->
```
## 类选择器
作用：查找标签，差异化设置标签的显示效果
步骤:
- 定义类选择器 --> `.类名`
- 使用类选择器 --> 标签添加`class='类名`
注意：
- 类名自定义，不要用纯数字或中文，尽量用英文命名
- 一个类选择器可以供多个标签使用
- 一个标签可以使用多个类名，类名之间用空格隔开

**开发习惯：类名见名知义，多个单词可以用`-`连接，例如：`news-hd`(新闻头部)**
```html
    <title>初识CSS</title>
    <style>
        /* 定义 */
        .red {
            color: red;
        }
    </style>
</head>
<body>
    <!-- 使用 -->
    <p class="red">这是p标签</p>
    <p>感谢朱哥</p>
    <div class="red">这是div标签</div>
</body>
```
```html
<style>
        /* 定义 */
        .red {
            color: red;
        }
        .size {
            font-size: 50px;
        }
    </style>
</head>
<body>
    <!-- 使用 -->
    <p class="red size">这是p标签</p>
    <p>感谢朱哥</p>
    <div class="red size">这是div标签</div>
</body>
```
**一个类可以为多个标签使用，一个标签可以使用多个类，注意使用多个类时的书写方法（类名用空格隔开）**
## id选择器
作用：查找标签，差异化设置标签的显示效果
场景：id选择器一般配合JavaScript使用，很少用来设置CSS样式
步骤：
- 定义id选择器 --> `#id名` 
- 使用id选择器 --> 标签添加`id="id名"`

*规则：同一个id选择器在一个页面只能使用一次*
```html
<style>
        /* 定义 */
        #brown {
            color: brown;
        }
    </style>
</head>
<body>
    <!-- 使用 -->
    <p>这是p标签</p>
    <p id="brown">感谢朱哥</p>
    <div >这是div标签</div>
</body>
```
# 通配符选择器
作用：查找页面所有标签，设置相同样式
通配符选择器:`*`,不需要调用，浏览器自动查找页面**所有**标签，设置相同的样式
```html
    <style>
        /* 定义 */
        * {
            color: blue;
        }
    </style>
</head>
<body>
    <!-- 使用 -->
    <p>这是p标签</p>
    <p>感谢朱哥</p>
    <div >这是div标签</div>
</body>
```
# 画盒子
目标：使用合适的选择器画盒子
新属性：
- `width`:宽度
- `height`:高度
- `background-color`:背景色
```html
<style>
        .red {
            width: 100px;
            height: 100px;
            background-color: brown;
        }
        .orange {
            width: 200px;
            height: 200px;
            background-color: orange;
        }
    </style>
</head>
<body>
    <div class="red">div1</div>
    <div class="orange">div2</div>
</body>
```
# 文字控制属性
常见属性:
- `font-size`:字体大小
  - 属性值:文字尺寸，PC端网页最常用的单位`px`(单位不能少)
```html
<style>
    p {
        font-size: 30px;
    }
</style>
```
- `font-weight`:字体粗细
  - 属性值：
    - 数字（更简单，开发使用）
      - 正常:`400`(无单位)
      - 加粗:`700`
    - 关键字
      - 正常:`normal`
      - 加粗:`bold`
```html
    <style>
        h3 {
            font-weight: 400;
        }
        div {
            font-weight: 700;
        }
    </style>
</head>
<body>
    <!-- 标题文字默认加粗 -->
    <h3>h3 标题</h3>
    <div>div 标签</div>
</body>
```
- `font-style`:字体倾斜
  - 作用：清除文字默认的倾斜效果
  - 属性值：
    - 正常（不倾斜）：`normal`
    - 倾斜:`italic`
```html
    <style>
        em {
            font-style: normal;
        }
        div {
            font-style: italic;
        }
    </style>
</head>
<body>
    <em>em 标签</em>
    <div>div 标签</div>
</body>
```
- `line-height`:行高（文字高度（默认`16px`）+上间距+下间距）
  - 测量方法：从一行文字的最顶端（最底端）量到下一行文字的最顶端（最底端）
  - 作用：设置多行文本的间距
  - 属性值：
    - `数字+px`
    - `数字`（当前标签`font-size`字号属性值的倍数）
    - 垂直居中技巧（只适用于单行文字）：行高属性值等于盒子高度属性值（文字本身是对齐的，让盒子适应文字）
```html
    <style>
        p {
            line-height: 30px;
        }
    </style>
</head>
<body>
    <p>中央气象台7月18日18时继续发布暴雨蓝色预警预计7月18日20时至19日20时云南西部和中南部、广西北部贵州南部和东部、重庆东南部湖南大部、湖北南部和东部江西中北部、安徽中南部江苏中南部、上海、浙江北部等地的部分地区有大到暴雨局地有大暴雨上述部分地区伴有短时强降水局地有雷暴大风等强对流天气</p>
</body>
```
```html
    <style>
        div {
            height: 100px;
            background-color: skyblue;
            line-height: 100px;
        }
    </style>
</head>
<body>
    <div>垂直居中</div>
</body>
```
- `font-family`:字体族
  - 属性名：字体名--`font-family: 楷体;`
  - `font-family:Microsoft YaHei, Heiti SC, tahoma, sans-serif`
  - ↑：`font-family`属性值可以书写多个字体名，各个字体名用逗号隔开，执行顺序是从左向右依次查找，直至找到可用的
- `font`:字体复合属性
  - 使用场景：设置网页文字公共样式
  - 复合属性：属性的简写方式，一个属性对应多个值的写法，各个属性值之间用空格隔开
  - `font:是否倾斜 是否加粗 字号/行高 字体` (必须按顺序书写，至少写上字号与字体，平时使用可以从一些大网站上复制过来就行)
```html
<style>
    div {
        font: italic 700 30px/2 楷体;
    }
</style>
```
- `text-indent`:文本缩进
  - 属性值：
    - `数字+px`
    - `数字+em`(推荐，常见，1em=当前标签的字号大小)

首行缩进两个字：
```css
p {
        text-indent: 2em;
    }
```
```html
<style>
        p {
            text-indent: 2em;
            font-size: 30px;
        }
        
    </style>
</head>
<body>
    <p>4月30日，我市召开2026年高质量发展推进会暨“强镇”发展大会。会议强调，牢牢把握高质量发展这个首要任务，完整准确全面贯彻新发展理念，牢固树立和践行正确政绩观，探索走出有特色重效益可持续的高质量发展兴化路径。</p>
</body>
```
- `text-align`:文本对齐
  - 属性值：
    - `left`:左对齐（默认）
    - `center`:居中对齐
    - `right`:右对齐
  - 对齐的是文字内容，标签所占区域没变
```html
    <style>
        h1 {
            text-align: center;
        }
        
    </style>
</head>
<body>
    <h1>测试对齐</h1>
</body>
```
*图片对齐：↓*
```html
    <style>
        div {
            text-align: center;
        }
    </style>
</head>
<body>
    <div> <img src="./噜噜.gif" alt="" title="噜噜"></div>
</body>
```
- `text-decoration`:修饰线
  - 属性值：
    - `none`:无
    - `underline`:下划线
    - `line-through`:删除线
    - `overline`:上划线
```html
    <style>
        a {
            text-decoration: none;
        }
        div {
            text-decoration: underline;
        }
        p {
            text-decoration: line-through;
        }
        span {
            text-decoration: overline;
        }
    </style>
</head>
<body>
    <a href="#">a 标签，去掉下划线</a>
    <div>div 标签，添加下划线</div>
    <p>p 标签，添加删除线</p>
    <span>span 标签，添加顶划线</span>
</body>
```
- `color`:颜色
  - 属性值：
    - 颜色关键词:颜色英文单词:`red`、`green`...-->学习测试
    - rgb表示法:`rgb`(r,g,b):r,g,b表示红绿蓝三原色，取值：0~255-->了解
    - rgba表示法：`rbga(r,g,b,a)`:a表示透明度，取值0~1(越靠近0越透明)-->开发使用，实现透明色
    - 十六进制表示法:`#RRGGBB`:`#000000`,`#ffcc00`,简写:`#000`,`#fc0` -->开发使用（从设计稿复制）
```html
    <style>
        h1 {
            color: rgb(123, 223, 99);
        }
        div {
            color: rgba(96, 50, 141, 0.59);
        }
        span {
            color: #c06161;
        }
        /* span {
            color: #c77;
        } */
    </style>
</head>
<body>
    <h1>h1 标签</h1>
    <div>div 标签</div>
    <span>span 标签</span>
</body>
```
**实际书写时，vscode提供直接的取色盘**
# 调试工具
作用：检查、调试代码；帮助程序员发现代码问题、解决问题
1. 打开调试工具(右键-检查 / F12)
2. 使用调试工具
![!\[alt text\] )](调试1.png)
![frontend/CSS/调试2.png](调试2.png)
复选框代表正在生效，可以取消勾选
刷新后均会重置
# 综合案例
网页制作思路：
- 从上到下，先整体再局部
- 先标签，再CSS美化
# 复合选择器
定义：由两个或多个基础选择器，通过不同的方式组合而成
作用：更准确、更高效的选择目标元素（标签）
## 后代选择器
选中某元素的 **所有** 后代元素
选择器写法：`父选择器 子选择器{CSS属性}`,父子选择器之间用空格隔开
```html
    <style>
        div span{
            color: aquamarine;
        }

    </style>
</head>
<body>
    <span>span标签</span>
    <div>
        <span>div子</span>
        <p>
            <span>div孙</span>
        </p>
    </div>
</body>
```
## 子代选择器
选中某元素的子代元素（最近的子级）
选择器写法：`父选择器>子选择器{CSS属性}`,父子选择器之间用`>`隔开
```html
    <style>
        div>span{
            color: aquamarine;
        }

    </style>
</head>
<body>
    <span>span标签</span>
    <div>
        <span>div子</span>
        <p>
            <span>div孙</span>
        </p>
    </div>
</body>
```
## 并集选择器
选中多组标签设置相同的样式
选择器写法：`选择器1,选择器2,...,选择器n{CSS属性}`,选择器之间用`,`隔开
*建议逗号后换行，结构更清晰*
```html
    <style>
        div,
        span,
        p {
            color: red;
        }
    </style>
</head>
<body>
    <div>这是div标签</div>
    <p>这是p标签</p>
    <span>这是span标签</span>
</body>
```
## 交集选择器-了解
选中同时满足多个条件的元素
选择器写法：`选择器1选择器2{CSS属性}`,选择器之间连写，没有任何符号
**注意：如果交集选择器中有标签选择器，标签选择器必须书写在最前面**
```html
    <style>
        p.box{
            color: red;
        }
    </style>
</head>
<body>
     <p class="box">p标签,使用了类选择器</p>
    <p>普通p标签</p>
    <div class="box">div标签,使用了类选择器</div>
</body>
<!-- 交集：满足是p且用了box类选择器 -->
```
# 伪类选择器
伪类表示元素状态，选中元素的某个状态设置样式
- 鼠标悬停状态：`选择器:hover{CSS属性}`(任何标签均可使用)
```html
    <style>
        a {
            color: aqua;
            text-decoration: none;
        }
        a:hover {
            color: blanchedalmond;
            text-decoration: underline;
        }
        .box:hover{
            color: rgb(44, 106, 160);
        }
    </style>
</head>
<body>
    <a href="#">a标签</a>
    <div class="box">div标签</div>
</body>
```
## 伪类-超链接（拓展）
超链接一共有四个状态：
- `:link`:访问前
- `:visited`:访问后
- `:hover`:鼠标悬停
- `:active`点击时(激活)
**提示：如果要给超链接设置以上四个状态，需要按LVHA的顺序书写**
```html
    <style>
        a:link{
            color: rgb(183, 123, 40);
        }
        a:visited{
            color: green;
        }
        a:hover{
            color: rgb(48, 162, 105);
        }
        a:active{
            color: rgb(162, 85, 127);
        }
    </style>
</head>
<body>
    <a href="#">a 标签</a>
</body>
<!-- 有一点需要注意：一个链接点击后默认已点击，则不可回到初始状态了 -->
```
**工作中，一个a标签选择器设置超链接的样式:hover状态设置（其他一般不设置）**
# CSS特性
CSS特性：化简代码/定位问题/并解决问题
## 继承性
子级默认继承父级的**文字控制属性**
```html
    <style>
        body{
            font-size: 30px;
            color: #09cfab;
            font-weight: 700;
        }
    </style>
</head>
<body>
    <!-- 当标签自己有样式（默认或设置）时，生效自己的样式 -->
    <div>div标签</div>
    <p>p标签</p>
    <span>span标签</span>
    <a href="#">a标签</a> <!--颜色没有继承，其他继承了-->
    <h1>h1标签</h1> <!--只继承了颜色-->
</body>
```
## 层叠性
特点：
- 相同的属性会覆盖：后面的CSS属性覆盖前面的CSS属性
- 不同的属性会叠加：不同的CSS属性都生效
```html
    <style>
        div {
            color: red;
            font-weight: 700;
        }
        div {
            color: bisque;
            font-size: 20px;
        }
    </style>
</head>
<body>
    <div>div标签</div>
</body>
```
## 优先级
也叫权重，当一个标签使用了多个选择器时，基于不同种类的选择器的匹配规则
公式：`通配符选择器<标签选择器<类选择器<id选择器<行内样式<!important`
*选中标签的范围越大，优先级越低*
```html
    <style>
        div {
            color: aqua;
        }
        * {
            color: red;
        }
        .box1 {
            color: rgb(148, 105, 48);
        }
        #box2 {
            color: blueviolet;
        }
    </style>
</head>
<body>
    <div>div标签</div>
    <div class="box1">div标签</div>
    <div class="box1" id="box2">div标签</div>
    <div class="box1" id="box2" style="color: brown;">div标签</div>
</body>
```
**提权至最高级（慎用）**
```html
<style>
        div {
            color: aqua;
        }
        * {
            color: red !important;
        }
        .box1 {
            color: rgb(148, 105, 48);
        }
        #box2 {
            color: blueviolet;
        }
    </style>
</head>
<body>
    <div>div标签</div>
    <div class="box1">div标签</div>
    <div class="box1" id="box2">div标签</div>
    <div class="box1" id="box2" style="color: brown;">div标签</div>
</body>
```
## 优先级-叠加计算规则
叠加计算：如果是复合选择器，则需要权重叠加计算
公式：（每一级之间不存在进位）
（行内样式，id选择器个数，类选择器个数，标签选择器个数）
规则：
- 从左向右一次比较选个数，同一级个数多的优先级高，如果个数相同，则向后比较
- `!important`权重最高
- 继承权重最低