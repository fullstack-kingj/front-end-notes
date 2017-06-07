## 概述

### 1）HTML 5 文档类型

Bootstrap 使用到的某些 HTML 元素和 CSS 属性需要将页面设置为 HTML5 文档类型。

```html
<!DOCTYPE html>
<html lang="zh-CN">
  ...
</html>
```

### 2）移动设备优先

Bootstrap 是移动设备优先的。为了确保适当的绘制和触屏缩放，需要在 `<head>` 之中添加 viewport 元元素。

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

在移动设备浏览器上，通过为 viewport设置 meta 属性为 user-scalable=no 可以禁用其缩放功能。这样禁用缩放功能后，用户只能滚动屏幕，就能让你的网站看上去更像原生应用的感觉。

```html
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">
```

### 3）排版与链接

Bootstrap 排版、链接样式设置了基本的全局样式。

* 为 body 元素设置 background-color: #fff;
* 使用 @font-family-base、@font-size-base 和 @line-height-base 变量作为排版的基本参数
* 为所有链接设置了基本颜色 @link-color ，并且当链接处于 :hover 状态时才添加下划线

## Normalize.css

### 1）CSS 重置样式库

为了增强跨浏览器表现的一致性，Bootstrap 使用 Normalize.css（CSS 重置样式库）。

### 2）什么是 Normalize.css

Normalize.css 只是一个很小的 CSS 文件，但它在默认的 HTML 元素样式上提供了跨浏览器的高度一致性。相比于传统的 CSS reset，Normalize.css 是一种现代的、为 HTML5 准备的优质替代方案。

Normalize.css 的主要特点如下：

* 保护有用的浏览器默认样式而不是完全去掉它
* 一般化的样式：为大部分HTML元素提供
* 修复浏览器自身的bug并保证各浏览器的一致性
* 优化CSS可用性：用一些小技巧
* 解释代码：用注释和详细的文档来

### 3）Normalize.css 与传统 Reset 的区别

* Normalize.css 保护了有价值的默认值
* Normalize.css 修复了浏览器的bug
* Normalize.css 不会让你的调试工具变的杂乱
* Normalize.css 是模块化的
* Normalize.css 拥有详细的文档

## 布局容器

Bootstrap 提供了以下两种布局容器：

* .container 类用于固定宽度并支持响应式布局的容器。

	| 媒体查询 | 宽度值 |
	| --- | --- |
	| >1200px | 1170px |
	| >992px | 970px |
	| >768px | 750px |
	| 小分辨率 | 100% |

* .container-fluid 类用于 100% 宽度，占据 viewport 的容器。

> **值得注意的是：**这两种 容器类不能互相嵌套。

## 按钮

### 1）作为按钮的元素

Bootstrap 利用 `<a>`、`<button>`和`<input>`元素作为按钮样式。

```html
<div class="container">
    <div class="row">
        <a class="btn btn-default" href="#" role="button">Link</a>
        <button class="btn btn-default" type="submit">Button</button>
        <input class="btn btn-default" type="button" value="Input">
        <input class="btn btn-default" type="submit" value="Submit">
    </div>
</div>
```

> **值得注意的是：**

> 1. 导航和导航条组件只支持 `<button>` 元素。
> 2. 如果 `<a>` 元素被作为按钮使用，务必为其设置 role="button" 属性。
> 3. 建议尽可能使用 `<button>` 元素。

### 2）预定义样式

Bootstrap 为按钮预定义了很多样式，具体样式说明如下：

| 样式名称 | 描述 |
| --- | --- |
| btn-default | 默认样式 |
| btn-primary | 首选项 |
| btn-success | 成功样式 |
| btn-info | 一般信息 |
| btn-warning | 警告样式 |
| btn-danger | 危险样式 |
| btn-link | 链接样式 |

```html
<div class="container">
    <div class="row">
        <button type="button" class="btn btn-default">（默认样式）Default</button>
        <button type="button" class="btn btn-primary">（首选项）Primary</button>
        <button type="button" class="btn btn-success">（成功）Success</button>
        <button type="button" class="btn btn-info">（一般信息）Info</button>
        <button type="button" class="btn btn-warning">（警告）Warning</button>
        <button type="button" class="btn btn-danger">（危险）Danger</button>
        <button type="button" class="btn btn-link">（链接）Link</button>
    </div>
</div>
```

### 3）不同尺寸的按钮

* Bootstrap 为按钮提供了大、默认、小和很小几个尺寸。

```html
<div class="container">
   <div class="row">
        <button type="button" class="btn btn-default btn-lg">（大按钮）Large button</button>
        <button type="button" class="btn btn-default">（默认尺寸）Default button</button>
        <button type="button" class="btn btn-default">（默认尺寸）Default button</button>
        <button type="button" class="btn btn-default btn-xs">（超小尺寸）Extra small button</button>
    </div>
</div>
```

* 通过给按钮添加 .btn-block 类可以将其拉伸至父元素100%的宽度，而且按钮也变为了块级（block）元素。

```html
<div class="container">
    <div class="row">
        <button type="button" class="btn btn-default btn-lg btn-block">（块级元素）Block level button</button>
    </div>
</div>
```

### 4）按钮激活状态

为按钮元素添加 .active 类，设置其为激活状态。当按钮处于激活状态时，其表现为被按压下去（底色更深、边框夜色更深、向内投射阴影）。

```html
<div class="container">
    <div class="row">
        <button type="button" class="btn btn-default btn-lg active">Button</button>
        <a href="#" class="btn btn-default btn-lg active" role="button">Link</a>
    </div>
</div>
```

### 5）按钮禁用状态

通过为按钮的背景设置 opacity 属性就可以呈现出无法点击的效果。

* 为 `<button>` 元素添加 disabled 属性，使其表现出禁用状态。

```html
<button type="button" class="btn btn-default btn-lg" disabled="disabled">Button</button>
```

> **跨浏览器兼容性**
>
> Internet Explorer 9 及更低版本的浏览器将会把按钮中的文本绘制为灰色，并带有恶心的阴影，目前还没有解决办法。

* 为基于 `<a>` 元素创建的按钮添加 .disabled 类。

```html
<a href="#" class="btn btn-default btn-lg disabled" role="button">Link</a>
```

## 图片

### 1）响应式图片

通过为图片添加 .img-responsive 类可以让图片支持响应式布局。

> 如果需要让使用了 .img-responsive 类的图片水平居中，请使用 .center-block 类，不要用 .text-center。

```html
<div class="container">
    <div class="row">
        <img src="imgs/1.jpg" class="img-responsive" alt="Responsive image">
    </div>
    <div class="row">
        <img src="imgs/1.jpg" class="img-responsive center-block" alt="Responsive image">
    </div>
</div>
```

### 2）图片形状

通过为 <img> 元素添加以下相应的类，可以让图片呈现不同的形状。

| 类名 | 描述 |
| --- | --- |
| img-rounded | 圆角矩形 |
| img-circle | 圆形 |
| img-thumbnail | 矩形 |

> IE 8 不支持 CSS3 中的圆角属性。

```html
<div class="container">
    <div class="row">
        <img src="imgs/1.jpg" alt="..." class="img-rounded">
        <img src="imgs/1.jpg" alt="..." class="img-circle">
        <img src="imgs/1.jpg" alt="..." class="img-thumbnail">
    </div>
</div>
```

## 文本

### 1）文本对齐

通过以下文本对齐类，可以简单方便的将文字重新对齐。

| 类名 | 描述 |
| --- | --- |
| text-left | 左对齐 |
| text-center | 居中对齐 |
| text-right | 右对齐 |
| text-justify | 两端对齐，段落中超出屏幕部分文字自动换行 |
| text-nowrap | 段落中超出屏幕部分不换行 |

```html
<div class="container">
    <div class="row">
        <p class="text-left">Left aligned text.</p>
        <p class="text-center">Center aligned text.</p>
        <p class="text-right">Right aligned text.</p>
        <p class="text-justify">Justified text.</p>
        <p class="text-nowrap">No wrap text.</p>
    </div>
</div>
```

### 2）改变大小写

通过以下这几个类可以改变文本的大小写。

| 类名 | 描述 |
| --- | --- |
| text-lowercase| 小写 |
| text-uppercase| 大写 |
| text-capitalize| 首字母大写 |

```html
<div class="container">
    <div class="row">
        <p class="text-lowercase">Lowercased text.</p>
        <p class="text-uppercase">Uppercased text.</p>
        <p class="text-capitalize">Capitalized text.</p>
    </div>
</div>
```

### 3）文本颜色

Bootstrap 允许为文本设置不同颜色表示不同含义，具体如下：

| 类名 | 描述 |
| --- | --- |
| text-muted | 提示，使用浅灰色 |
| text-primary | 首选项，使用蓝色 |
| text-success | 成功，使用浅绿色 |
| text-info | 信息，使用浅蓝色 |
| text-warning | 警告，使用黄色 |
| text-danger | 危险，使用褐色 |

```html
<div class="container">
    <div class="row">
        <p class="text-muted">提示信息</p>
        <p class="text-primary">首选项</p>
        <p class="text-success">成功</p>
        <p class="text-info">信息</p>
        <p class="text-warning">警告</p>
        <p class="text-danger">危险</p>
    </div>
</div>
```

## 列表

### 1）无序列表

```html
<div class="container">
    <div class="row">
        <ul>
            <li>苹果</li>
            <li>香蕉</li>
            <li>西瓜
                <ul>
                    <li>大兴西瓜</li>
                    <li>东北西瓜</li>
                </ul>
            </li>
            <li>芒果</li>
            <li>樱桃</li>
        </ul>
    </div>
</div>
```

### 2）有序列表

```html
<div class="container">
    <div class="row">
        <ol>
            <li>苹果</li>
            <li>香蕉</li>
            <li>西瓜
                <ol>
                    <li>大兴西瓜</li>
                    <li>东北西瓜</li>
                </ol>
            </li>
            <li>芒果</li>
            <li>樱桃</li>
        </ol>
    </div>
</div>
```

### 3）无样式列表

移除了默认的 list-style 样式和左侧外边距的一组元素（只针对直接子元素）。

```html
<div class="container">
    <div class="row">
        <ul class="list-unstyled">
            <li>苹果</li>
            <li>香蕉</li>
            <li>西瓜
                <ul>
                    <li>大兴西瓜</li>
                    <li>东北西瓜</li>
                </ul>
            </li>
            <li>芒果</li>
            <li>樱桃</li>
        </ul>
    </div>
</div>
```

### 4）内联列表

通过设置 display: inline-block; 并添加少量的内补（padding），将所有元素放置于同一行。

```html
<div class="container">
    <div class="row">
        <ul class="list-inline">
            <li>苹果</li>
            <li>香蕉</li>
            <li>西瓜
                <ul>
                    <li>大兴西瓜</li>
                    <li>东北西瓜</li>
                </ul>
            </li>
            <li>芒果</li>
            <li>樱桃</li>
        </ul>
    </div>
</div>
```

### 5）描述

#### a. 垂直排列的描述

带有描述的短语列表。

```html
<div class="container">
    <div class="row">
        <dl>
            <dt>Description lists</dt>
            <dd>A description list is perfect for defining terms.</dd>
            <dt>Euismod</dt>
            <dd>Vestibulum id ligula porta felis euismod semper eget lacinia odio sem nec elit.<br>
                Donec id elit non mi porta gravida at eget metus.</dd>
            <dt>Malesuada porta</dt>
            <dd>Etiam porta sem malesuada magna mollis euismod.</dd>
        </dl>
    </div>
</div>
```

#### b. 水平排列的描述

.dl-horizontal 可以让 <dl> 内的短语及其描述排在一行。

```html
<div class="container">
    <div class="row">
        <dl class="dl-horizontal">
            <dt>Description lists</dt>
            <dd>A description list is perfect for defining terms.</dd>
            <dt>Euismod</dt>
            <dd>Vestibulum id ligula porta felis euismod semper eget lacinia odio sem nec elit.<br>
                Donec id elit non mi porta gravida at eget metus.</dd>
            <dt>Malesuada porta</dt>
            <dd>Etiam porta sem malesuada magna mollis euismod.</dd>
        </dl>
    </div>
</div>
```

## 表格

### 1）基本表格

为任意 `<table>` 标签添加 .table 类可以为其赋予基本的样式。

```html
<div class="container">
    <div class="row">
        <table class="table">
            <thead>
            <tr>
                <th>ID</th>
                <th>名称</th>
                <th>价格</th>
            </tr>
            </thead>
            <tbody>
            <tr>
                <td>1</td>
                <td>书籍</td>
                <td>12.50</td>
            </tr>
            <tr>
                <td>2</td>
                <td>电视</td>
                <td>1000</td>
            </tr>
            <tr>
                <td>3</td>
                <td>笔记本</td>
                <td>2000</td>
            </tr>
            <tr>
                <td>3</td>
                <td>笔记本</td>
                <td>2000</td>
            </tr>
            </tbody>
        </table>
    </div>
</div>
```

### 2）条纹状表格

通过 .table-striped 类可以给 `<tbody>` 之内的每一行增加斑马条纹样式。


```html
<div class="container">
    <div class="row">
        <table class="table table-striped">
            <thead>
            <tr>
                <th>ID</th>
                <th>名称</th>
                <th>价格</th>
            </tr>
            </thead>
            <tbody>
            <tr>
                <td>1</td>
                <td>书籍</td>
                <td>12.50</td>
            </tr>
            <tr>
                <td>2</td>
                <td>电视</td>
                <td>1000</td>
            </tr>
            <tr>
                <td>3</td>
                <td>笔记本</td>
                <td>2000</td>
            </tr>
            <tr>
                <td>3</td>
                <td>笔记本</td>
                <td>2000</td>
            </tr>
            </tbody>
        </table>
    </div>
</div>
```

> 条纹状表格是依赖 :nth-child CSS 选择器实现的，而这一功能不被 IE 8 支持。

### 3）带边框表格

添加 .table-bordered 类为表格和其中的每个单元格增加边框。

```html
<div class="container">
    <div class="row">
        <table class="table table-bordered">
            <thead>
            <tr>
                <th>ID</th>
                <th>名称</th>
                <th>价格</th>
            </tr>
            </thead>
            <tbody>
            <tr>
                <td>1</td>
                <td>书籍</td>
                <td>12.50</td>
            </tr>
            <tr>
                <td>2</td>
                <td>电视</td>
                <td>1000</td>
            </tr>
            <tr>
                <td>3</td>
                <td>笔记本</td>
                <td>2000</td>
            </tr>
            <tr>
                <td>3</td>
                <td>笔记本</td>
                <td>2000</td>
            </tr>
            </tbody>
        </table>
    </div>
</div>
```

### 4）鼠标悬停

通过添加 .table-hover 类可以让 `<tbody>` 中的每一行对鼠标悬停状态作出响应。

```html
<div class="container">
    <div class="row">
        <table class="table table-hover">
            <thead>
            <tr>
                <th>ID</th>
                <th>名称</th>
                <th>价格</th>
            </tr>
            </thead>
            <tbody>
            <tr>
                <td>1</td>
                <td>书籍</td>
                <td>12.50</td>
            </tr>
            <tr>
                <td>2</td>
                <td>电视</td>
                <td>1000</td>
            </tr>
            <tr>
                <td>3</td>
                <td>笔记本</td>
                <td>2000</td>
            </tr>
            <tr>
                <td>3</td>
                <td>笔记本</td>
                <td>2000</td>
            </tr>
            </tbody>
        </table>
    </div>
</div>
```

### 5）紧缩表格

通过添加 .table-condensed 类可以让表格更加紧凑，单元格中的 padding 均会减半。

```html
<div class="container">
    <div class="row">
        <table class="table table-condensed">
            <thead>
            <tr>
                <th>ID</th>
                <th>名称</th>
                <th>价格</th>
            </tr>
            </thead>
            <tbody>
            <tr>
                <td>1</td>
                <td>书籍</td>
                <td>12.50</td>
            </tr>
            <tr>
                <td>2</td>
                <td>电视</td>
                <td>1000</td>
            </tr>
            <tr>
                <td>3</td>
                <td>笔记本</td>
                <td>2000</td>
            </tr>
            <tr>
                <td>3</td>
                <td>笔记本</td>
                <td>2000</td>
            </tr>
            </tbody>
        </table>
    </div>
</div>
```

### 6）状态类

通过这些状态类可以为行或单元格设置颜色。

| 类名 | 描述 |
| --- | --- |
| active | 鼠标悬停在行或单元格上时所设置的颜色 |
| success | 标识成功或积极的动作 |
| info | 标识普通的提示信息或动作 |
| warning | 标识警告或需要用户注意 |
| danger | 标识危险或潜在的带来负面影响的动作 | 

```html
<div class="container">
    <div class="row">
        <table class="table">
            <thead>
            <tr>
                <th>ID</th>
                <th>名称</th>
                <th>价格</th>
            </tr>
            </thead>
            <tbody>
            <tr class="active">
                <td>1</td>
                <td>书籍</td>
                <td>12.50</td>
            </tr>
            <tr class="success">
                <td>2</td>
                <td>电视</td>
                <td>1000</td>
            </tr>
            <tr>
                <td class="info">3</td>
                <td>笔记本</td>
                <td class="warning">2000</td>
            </tr>
            <tr>
                <td>3</td>
                <td class="danger">笔记本</td>
                <td>2000</td>
            </tr>
            </tbody>
        </table>
    </div>
</div>
```

> **值得注意的是：**
> 
> 这些状态类不仅可以作用于`<tr>`元素，还可以作用于`<td>`元素。

### 7）响应式表格

将任何 .table 元素包裹在 .table-responsive 元素内，即可创建响应式表格。其会在小屏幕设备上（小于768px）水平滚动。当屏幕大于 768px 宽度时，水平滚动条消失。

## 辅助样式

### 1）背景颜色

和文本颜色一样，Bootstrap 允许添加不同的背景颜色表示不同含义，具体如下：

| 类名 | 描述 |
| --- | --- |
| bg-primary | 首选项，使用蓝色 |
| bg-success | 成功，使用浅绿色 |
| bg-info | 信息，使用浅蓝色 |
| bg-warning | 警告，使用黄色 |
| bg-danger | 危险，使用褐色 |

```html
<div class="container">
    <div class="row">
        <p class="bg-muted">提示信息</p>
        <p class="bg-primary">首选项</p>
        <p class="bg-success">成功</p>
        <p class="bg-info">信息</p>
        <p class="bg-warning">警告</p>
        <p class="bg-danger">危险</p>
    </div>
</div>
```

### 2）浮动

#### a. 浮动

通过添加 .pull-left 或 .pull-right 类，可以将任意元素向左或向右浮动。

* CSS 代码

```css
.block1 {
	width : 300px;
	height : 200px;
	border : 1px solid black;
	background : dodgerblue;
}
.block2 {
	width : 500px;
	height : 300px;
	border : 1px solid black;
	background : yellowgreen;
}
```

* HTML 代码

```html
<div class="container">
    <div>
        <div class="block1 pull-left"></div>
        <div class="block1 pull-right"></div>
    </div>
    <div class="block2"></div>
</div>
```

#### b. 清除浮动

通过为父元素添加 .clearfix 类可以很容易地清除浮动。

* CSS 代码

```css
.block1 {
	width : 300px;
	height : 200px;
	border : 1px solid black;
	background : dodgerblue;
}
.block2 {
	width : 500px;
	height : 300px;
	border : 1px solid black;
	background : yellowgreen;
}
```

* HTML 代码

```html
<div class="container">
    <div class="clearfix">
        <div class="block1 pull-left"></div>
        <div class="block1 pull-right"></div>
    </div>
    <div class="block2"></div>
</div>
```

### 3）居中

为任意元素设置 .center-block 类让其中的内容居中。

```html
<div class="center-block"></div>
```

### 4）显示或隐藏

.show 和 .hidden 类可以强制任意元素显示或隐藏(对于屏幕阅读器也能起效)，这些类只对块级元素起作用。

另外，.invisible 类可以被用来仅仅影响元素的可见性，也就是说，元素的 display 属性不被改变，并且这个元素仍然能够影响布局。

```html
<div class="show"></div>
<div class="hidden"></div>
<div class="invisible"></div>
<div></div>
```

## 栅格系统

### 1）什么是栅格系统

栅格系统用于通过一系列的行（row）与列（column）的组合来创建页面布局，内容就可以放入这些创建好的布局中。

Bootstrap 提供的栅格系统，主要特点如下：

* 行的宽度，可以是固定宽度，也可以是相对宽度（100%）。
* 一行中最多可以包含 12 个列。如果一行中包含的列大于 12，多余的列则被作为一个整体另起一行排列。
* Bootstrap 根据 4 种分辨率提供不同的栅格系统预定义样式。

### 2）栅格系统工作原理

Bootstrap 的栅格系统的工作原理如下：

* 栅格系统必须指定一个容器元素，该元素的 class 必须为 .container（固定宽度）或 .container-fluid（100%宽度）。
* 作为“行”的元素必须作为容器元素的直接子元素，并且 class 设置为 .row。
* 作为“列”的元素必须是“行”元素的直接子元素（**“行”元素的子元素不能直接包含内容，内容应该被包含在“列”元素中。**），并且一行最多允许创建 12 列。
* “列”元素的预定义样式，具体内容请参考 *“3）栅格系统的参数”* 内容。

### 3）栅格系统的参数

Bootstrap 根据 4 种不同的分辨率提供了不同的预定义样式（栅格类）。栅格类适用于与屏幕宽度大于或等于分界点大小的设备 ， 并且针对小屏幕设备覆盖栅格类。

| | **超小屏幕** 手机（<768px）| **小屏幕** 平板（>=768px）| **中等屏幕** 桌面显示器（>=992px）| **大屏幕** 大桌面显示器（>=1200px）|
| --- | --- | --- | --- | --- |
| 栅格系统行为 | 总是水平排列 | 以折叠开始，大于断点成水平方式 | 以折叠开始，大于断点成水平方式 | 以折叠开始，大于断点成水平方式 |
| 容器宽度 | None（自动）| 750px | 970px | 1170px |
| class 前缀 | .col-xs- | .col-sm- | .col-md- | .col-lg- |
| 列数 | 12 | 12 | 12 | 12 |
| 列宽 | 自动 | 60px | 78px | 95px |
| 槽宽 | 30px（每列左右均为 15px）| 30px（每列左右均为 15px）| 30px（每列左右均为 15px）| 30px（每列左右均为 15px）|
| 可嵌套 | 是 | 是 | 是 | 是 |
| 偏移 | 是 | 是 | 是 | 是 |
| 排序 | 是 | 是 | 是 | 是 |

### 4）栅格系统示例

* CSS 代码

```css
body {
	margin-top : 100px;
}
[class*=col-] {
	border : 1px solid black;
	padding-top: 15px;
	padding-bottom: 15px;
}
```

* HTML 代码

```html
<div class="container">
    <h3>三等分列</h3>
    <div class="row">
        <div class="col-md-4">.col-md-4</div>
        <div class="col-md-4">.col-md-4</div>
        <div class="col-md-4">.col-md-4</div>
    </div>
    <h3>三不等分列</h3>
    <div class="row">
        <div class="col-md-3">.col-md-3</div>
        <div class="col-md-6">.col-md-6</div>
        <div class="col-md-3">.col-md-3</div>
    </div>
    <h3>手机、平板电脑和PC桌面不同布局</h3>
    <div class="row">
        <div class="col-md-3 col-sm-6 col-xs-12">col-md-3 col-sm-6 col-xs-12</div>
        <div class="col-md-3 col-sm-6 col-xs-12">col-md-3 col-sm-6 col-xs-12</div>
        <div class="col-md-3 col-sm-6 col-xs-12">col-md-3 col-sm-6 col-xs-12</div>
        <div class="col-md-3 col-sm-6 col-xs-12">col-md-3 col-sm-6 col-xs-12</div>
    </div>
</div>
```

### 5）调整列的顺序

#### a. 列偏移

使用 .col-md-offset-* 类可以将列向右侧偏移。（`*` 表示向右偏移的列数）

```html
<div class="container">
    <h3>列偏移</h3>
    <div class="row">
        <div class="col-md-4">.col-md-4</div>
        <div class="col-md-4 col-md-offset-4">.col-md-4 .col-md-offset-4</div>
    </div>
    <div class="row">
        <div class="col-md-3 col-md-offset-3">.col-md-3 .col-md-offset-3</div>
        <div class="col-md-3 col-md-offset-3">.col-md-3 .col-md-offset-3</div>
    </div>
    <div class="row">
        <div class="col-md-6 col-md-offset-3">.col-md-6 .col-md-offset-3</div>
    </div>
</div>
```

#### b. 嵌套列

在 Bootstrap 的栅格系统允许进行嵌套。所谓**栅格系统嵌套**，就是指在 Bootstrap 栅格系统中的每列中允许包含一个栅格系统。

> 被嵌套的“行”中所包含的列的个数依旧不能超过 12 列。

```html
<div class="container">
    <h3>嵌套列</h3>
    <div class="row">
        <div class="col-sm-9">
            Level 1: .col-sm-9
            <div class="row">
                <div class="col-xs-8 col-sm-6">Level 2: .col-xs-8 .col-sm-6</div>
                <div class="col-xs-4 col-sm-6">Level 2: .col-xs-4 .col-sm-6</div>
            </div>
        </div>
    </div>
</div>
```

#### c. 列排序

通过将栅格系统中的列向右移动（push）或向左移动（pull）来改变列的顺序。

* `.col-md-push-*`表示向右移动
* `.col-md-pull-*`表示向左移动

```html
<div class="container">
    <h3>列排序</h3>
    <div class="row">
        <div class="col-md-9 col-md-push-3">.col-md-9 .col-md-push-3</div>
        <div class="col-md-3 col-md-pull-9">.col-md-3 .col-md-pull-9</div>
    </div>
</div>
``` 

### 6）响应式工具

通过单独或联合使用以下列出的 class，可以针对不同屏幕尺寸隐藏或显示页面内容。

| | **超小屏幕** 手机（<768px）| **小屏幕** 平板（>=768px）| **中等屏幕** 桌面（>=992px）| **大屏幕** 大桌面（>=1200px）|
| --- | :---: | :---: | :---: | :---: |
| .hidden-xs | 隐藏 | 可见 | 可见 | 可见 |
| .hidden-sm | 可见 | 隐藏 | 可见 | 可见 |
| .hidden-md | 可见 | 可见 | 隐藏 | 可见 |
| .hidden-lg | 可见 | 可见 | 可见 | 隐藏 |

```html
<div class="container">
    <h3>响应式工具</h3>
    <div class="row">
        <div class="col-md-3 col-sm-4 hidden-xs">.col-md-3</div>
        <div class="col-md-6 col-sm-8 col-xs-12">.col-md-6</div>
        <div class="col-md-3 hidden-sm hidden-xs">.col-md-3</div>
    </div>
</div>
```

### 7）响应式栅格系统示例

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Bootstrap栅格系统案例</title>

    <!-- Bootstrap -->
    <link href="bootstrap/css/bootstrap.min.css" rel="stylesheet">

    <!--[if lt IE 9]>
    <script src="bootstrap/js/html5shiv.min.js"></script>
    <script src="bootstrap/js/respond.min.js"></script>
    <![endif]-->
</head>
<body>
<div class="jumbotron">
    <div class="container">
        <h1>Hello, world!</h1>
        <p>This is a template for a simple marketing or informational website. It includes a large callout called a
            jumbotron and three supporting pieces of content. Use it as a starting point to create something more
            unique.</p>
    </div>
</div>

<div class="container">
    <!-- Example row of columns -->
    <div class="row">
        <div class="col-md-4">
            <h2>Heading</h2>
            <p>Donec id elit non mi porta gravida at eget metus. Fusce dapibus, tellus ac cursus commodo, tortor mauris
                condimentum nibh, ut fermentum massa justo sit amet risus. Etiam porta sem malesuada magna mollis
                euismod. Donec sed odio dui. </p>
            <p><a class="btn btn-default" href="#" role="button">View details &raquo;</a></p>
        </div>
        <div class="col-md-4">
            <h2>Heading</h2>
            <p>Donec id elit non mi porta gravida at eget metus. Fusce dapibus, tellus ac cursus commodo, tortor mauris
                condimentum nibh, ut fermentum massa justo sit amet risus. Etiam porta sem malesuada magna mollis
                euismod. Donec sed odio dui. </p>
            <p><a class="btn btn-default" href="#" role="button">View details &raquo;</a></p>
        </div>
        <div class="col-md-4">
            <h2>Heading</h2>
            <p>Donec sed odio dui. Cras justo odio, dapibus ac facilisis in, egestas eget quam. Vestibulum id ligula
                porta felis euismod semper. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut
                fermentum massa justo sit amet risus.</p>
            <p><a class="btn btn-default" href="#" role="button">View details &raquo;</a></p>
        </div>
    </div>

    <hr>

    <footer>
        <p>&copy; 2015 Company, Inc.</p>
    </footer>
</div>

<script src="bootstrap/js/jquery-1.11.3.js"></script>
<script src="bootstrap/js/bootstrap.min.js"></script>
</body>
</html>
```

## 表单

### 1）基本表单

Bootstrap 为单独的表单元素预定义了全局样式，表单内元素的具体使用如下：

* 设置了 .form-control 类的 `<input>`、`<textarea>` 和 `<select>` 元素都将被默认设置宽度属性为 width: 100%;。
* 将 label 元素和前面提到的控件包裹在 .form-group 中可以获得最好的排列。

```html
<div class="container">
    <div class="row">
        <form>
            <div class="form-group">
                <label for="exampleInputEmail1">Email address</label>
                <input type="email" class="form-control" id="exampleInputEmail1" placeholder="Email">
            </div>
            <div class="form-group">
                <label for="exampleInputPassword1">Password</label>
                <input type="password" class="form-control" id="exampleInputPassword1" placeholder="Password">
            </div>
            <button type="submit" class="btn btn-default">Submit</button>
        </form>
    </div>
</div>
```

### 2）内联表单

为 `<form>` 元素添加 .form-inline 类可使其内容左对齐并且表现为 inline-block 级别的控件。

> 只适用于 viewport 至少在 768px 宽度时（视口宽度再小的话就会使表单折叠）。

```html
<div class="container">
    <div class="row">
        <form class="form-inline">
            <div class="form-group">
                <label for="exampleInputName2">Name</label>
                <input type="text" class="form-control" id="exampleInputName2" placeholder="Jane Doe">
            </div>
            <div class="form-group">
                <label for="exampleInputEmail2">Email</label>
                <input type="email" class="form-control" id="exampleInputEmail2" placeholder="jane.doe@example.com">
            </div>
            <button type="submit" class="btn btn-default">Send invitation</button>
        </form>
    </div>
</div>
```

> **需要注意的是：**
> 
> 在内联表单，我们将这些元素的宽度设置为 width: auto;，因此，多个控件可以排列在同一行。
> 
> 如果你没有为每个输入控件设置 label 标签，屏幕阅读器将无法正确识别。对于这些内联表单，你可以通过为 label 设置 .sr-only 类将其隐藏。

```html
<div class="container">
    <div class="row">
        <form class="form-inline">
            <div class="form-group">
                <label class="sr-only" for="exampleInputEmail3">Email address</label>
                <input type="email" class="form-control" id="exampleInputEmail3" placeholder="Email">
            </div>
            <div class="form-group">
                <label class="sr-only" for="exampleInputPassword3">Password</label>
                <input type="password" class="form-control" id="exampleInputPassword3" placeholder="Password">
            </div>
            <button type="submit" class="btn btn-default">Sign in</button>
        </form>
    </div>
</div>
```

### 3）水平排列的表单

通过为表单添加 .form-horizontal 类，并联合使用 Bootstrap 预置的栅格类，可以将 label 标签和控件组水平并排布局。

> 这样做将改变 .form-group 的行为，使其表现为栅格系统中的行（row），因此就无需再额外添加 .row 了。

```html
<div class="container">
    <div class="row">
        <form class="form-horizontal">
            <div class="form-group">
                <label for="inputEmail3" class="col-sm-2 control-label">Email</label>
                <div class="col-sm-10">
                    <input type="email" class="form-control" id="inputEmail3" placeholder="Email">
                </div>
            </div>
            <div class="form-group">
                <label for="inputPassword3" class="col-sm-2 control-label">Password</label>
                <div class="col-sm-10">
                    <input type="password" class="form-control" id="inputPassword3" placeholder="Password">
                </div>
            </div>
            <div class="form-group">
                <div class="col-sm-offset-2 col-sm-10">
                    <button type="submit" class="btn btn-default">Sign in</button>
                </div>
            </div>
        </form>
    </div>
</div>
```

### 4）单选框和多选框

#### a. 默认外观

* 单选框使用 class 为 .radio
* 多选框使用 class 为 .checkbox

单选框或多选框的样式要定义在 div 元素中（该元素作为容器元素，包含文本和单选或多选框元素）。

```html
<div class="container">
    <div class="row">
        <form>
            <div class="checkbox">
                <label>
                    <input type="checkbox" value="">
                    Option one is this and that&mdash;be sure to include why it's great
                </label>
            </div>
            <div class="checkbox disabled">
                <label>
                    <input type="checkbox" value="" disabled>
                    Option two is disabled
                </label>
            </div>

            <div class="radio">
                <label>
                    <input type="radio" name="optionsRadios" id="optionsRadios1" value="option1" checked>
                    Option one is this and that&mdash;be sure to include why it's great
                </label>
            </div>
            <div class="radio">
                <label>
                    <input type="radio" name="optionsRadios" id="optionsRadios2" value="option2">
                    Option two can be something else and selecting it will deselect option one
                </label>
            </div>
            <div class="radio disabled">
                <label>
                    <input type="radio" name="optionsRadios" id="optionsRadios3" value="option3" disabled>
                    Option three is disabled
                </label>
            </div>
        </form>
    </div>
</div>
```

#### b. 内联单选和多选框

通过将 .checkbox-inline 或 .radio-inline 类应用到一系列的多选框（checkbox）或单选框（radio）控件上，可以使这些控件排列在一行。

```html
<div class="container">
    <div class="row">
        <form>
            <label class="checkbox-inline">
                <input type="checkbox" id="inlineCheckbox1" value="option1"> 1
            </label>
            <label class="checkbox-inline">
                <input type="checkbox" id="inlineCheckbox2" value="option2"> 2
            </label>
            <label class="checkbox-inline">
                <input type="checkbox" id="inlineCheckbox3" value="option3"> 3
            </label>

            <label class="radio-inline">
                <input type="radio" name="inlineRadioOptions" id="inlineRadio1" value="option1"> 1
            </label>
            <label class="radio-inline">
                <input type="radio" name="inlineRadioOptions" id="inlineRadio2" value="option2"> 2
            </label>
            <label class="radio-inline">
                <input type="radio" name="inlineRadioOptions" id="inlineRadio3" value="option3"> 3
            </label>
        </form>
    </div>
</div>
```