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
