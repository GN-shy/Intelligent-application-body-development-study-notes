#                                                         css文本样式

## 概述

CSS文本样式用于控制网页中文字的外观，包括字体，颜色，对齐，间距等，主要分为了两大类：

1. 字体样式：比如使用哪种字体，字体大小，字体粗体，斜体，等等
2. 文本布局：文本对齐、行高、字间距、首行缩进等

* 文字是无法直接通过css来更改样式的，必须要用适合的标签来包裹它们，本质是修改标签样式，里面文字跟随样式变化

## 字体样式

| 字体样式          | 说明         |
| ----------------- | ------------ |
| `color`           | 设置字体颜色 |
| `font-family`     | 字体族       |
| `font-size`       | 字体大小     |
| `font-style`      | 字体风格     |
| `font-weight`     | 字体粗体     |
| `text-decoration` | 字体装饰     |

### 字体颜色color

1. 关键字

   这些颜色通常不会在生产环境的网站中使用，主要学习使用。比如：red，green，blue

2. 十六进制

   这个是开发最常用的，实际开发中，从设计稿直接复制即可。比如红色#FF0000或者#F00

3. rgb格式

​     rgb()函数接受三个参数，分别表示颜色的红，绿，蓝。也是设计稿复制。比如红色 rgb(255,0,0)，第四个值是透明度值



### 字体族

给定一个有先后顺序的，由字体名或者字体族名组成的列表来选定的元素设置字体

```
body {
  font-family: Arial, Helvetica, sans-serif;
}
```

- **说明**：属性值用逗号隔开，浏览器会选择列表中第一个该计算机上已安装的字体。

- **开发提示**：实际开发中，这类字体栈都是规定好的，可以直接复制使用，无需记忆。

  ​               

  ###  字体大小 font-size

  ```
  p {
      font-size: 18px;
  }
  ```

  像素px：CSS像素是CSS中用于定义长度，尺寸的单位    `绝对单位`

  不同浏览器默认字体大小不一样，谷歌默认16px，建议给body标签统一指定大小，做到浏览器统一

  ​

  ### 字体风格 font-style

  属性值：

  - normal：将文本设置为普通字体
  - italic：如果当前字体的斜体版本可用，那么文本设置为斜体版本

  左侧代码（`<p>` 标签设置斜体）

  ```css
  p {
    font-style: italic; /* 设置斜体样式 */
  }
  ```

  右侧代码（`<em>` 标签取消斜体）

  ```css
  em {
    font-style: normal; /* 让em取消斜体 */
  }
  ```

  最常见：让 `em` 或者 `i` 标签取消默认倾斜
  ​

  ### 字体粗体font-weight

   font-weight 用于设置文字的粗细程度。

  使用场景：

  1. 很多标题不需要加粗时，可通过 CSS 取消默认加粗。

  2. 对大批量文字进行批量加粗处理。

     属性值：

  - **`normal`**：正常粗细
  - **`bold`**：加粗
  > 其他值受字体属性影响，实际开发中基本不用。

  数字属性值

  - **`400`**：等价于 `normal`，正常粗细
  - **`700`**：等价于 `bold`，加粗
  > 取值范围为 `100~900`，实际开发中最常用的就是 `400` 和 `700`。

  代码示例

  ```css
  /* 正常粗细 */
  .text-normal {
    font-weight: normal;
    /* 等价于 font-weight: 400; */
  }

  /* 加粗 */
  .text-bold {
    font-weight: bold;
    /* 等价于 font-weight: 700; */
  }
  ```

  ---

  ​

  ### 字体装饰 `text-decoration`

  `text-decoration` 用于设置或取消文本上的装饰线条。

  #### 使用场景

  1. 最常见的场景是处理链接下划线，比如取消链接默认的下划线。
  2. 特殊排版需求下，为文本添加删除线等装饰。

  ------

  #### 属性值

  - **none**：取消所有文本装饰
  - **underline**：添加下划线
  - **overline**：添加上划线
  - **line-through**：添加穿过文本的删除线

  ------

  #### 代码示例

  css

  ```
  /* 取消链接下划线（最常用） */
  a {
    text-decoration: none;
  }

  /* 为文本添加下划线 */
  .underline {
    text-decoration: underline;
  }

  /* 为文本添加删除线 */
  .delete {
    text-decoration: line-through;
  }
  ```

  ###  总结

  | 属性              | 描述               | 常见取值                                                     | 示例                                                         |
  | ----------------- | ------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
  | `color`           | 设置文本内容的颜色 | 颜色名称 (red, blue)、十六进制 (#ff0000)、RGB (rgb (255,0,0))、RGBA (rgba (255,0,0,0.5)) | `color: red;``color: #3366cc;`                               |
  | `font-family`     | 设置文本的字体系列 | 无衬线字体等                                                 | `font-family: "Microsoft YaHei", sans-serif;`                |
  | `font-size`       | 设置文本的大小     | `px` 等单位                                                  | `font-size: 16px;`                                           |
  | `font-style`      | 设置文本的样式     | `normal`(正常)、`italic`(斜体)                               | `font-style: normal;`                                        |
  | `font-weight`     | 设置文本的粗细     | 数值 (100-900)、关键字 (`normal`, `bold`)                    | `font-weight: 400;``font-weight: 700;`                       |
  | `text-decoration` | 设置文本的装饰效果 | `none`(无装饰)、`underline`(下划线)、`overline`(上划线)、`line-through`(中划线) | `text-decoration: underline;``text-decoration: line-through;` |




### font简写

font简写属性在一个声明中设置多个字体属性

使用场景：给整个页面设置相关字体样式

语法：**font: font-style font-weight  font-size/line-height   font-family**

- 其中font-size和font-family必须写
- 其他可用省略，默认显示


## 页面布局

比如：文本对齐，行高，字间距，首行缩进等

注意：文字是无法直接通过CSS来更改样式的，必须要用适合的标签来包裹它们，本质是修改标签样式，里面文字跟随样式变化

| 字体样式         | 说明         |
| ---------------- | ------------ |
| `text-align`     | 文本对齐     |
| `text-indent`    | 首行缩进     |
| `letter-spacing` | 文本字符间距 |
| `line-height`    | 行高         |



### 文本对齐 text-align

控制文本在它所在的块级盒子内如何水平对齐

使用场景：

- 文本/图片在盒子水平对齐

- 文章文字两端对齐

  属性值：

  left: 文本左对齐（默认）

  right: 文本右对齐

  center:文本水平居中对齐

  justify: 自动改变字间距，两端对齐



### 首行缩进 text-indent

设置块级元素中本行前面空格（缩进）的长度

使用场景：

- 段落首行缩进2个字的效果
- logo隐藏文字效果

属性值：数字

常见单位是em，相对单位，本元素的文字大小1em等于当前元素的字体大小，如果当前元素没有大小，则按照父元素文字大小



首行缩进两个字：

```
p{
    text-indent: 2em;
}
```

