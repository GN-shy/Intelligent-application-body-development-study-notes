## 字体图标

字体图标是一种将图标以**字体形式**嵌入网页的技术，允许开发者像使用文字一样通过css控制**图标的样式**（如颜色，大小，阴影等）

使用场景：

- 导航菜单图标
- 按钮操作图标
- 结合动画效果

优势：

1.  **矢量缩放**：无损放大缩小
2.  **样式灵活**：通过 CSS 直接修改颜色、大小、阴影等属性。
3.  **减少 HTTP 请求**：一个字体文件可包含多个图标，比多张图片更高效。
4.  **兼容性好**：支持所有现代浏览器，甚至部分旧版浏览器。

如何使用：

1. 下载字体图标文件

   去官网或者设计师准备字体图标文件，保存到项目目录下。

2. 引入html文件中

根据提供的压缩包，引入CSS文件（link方式）。

3. 使用字体图标

一般情况下，我们通过标签调用类名选择对应字体图标。
根据实际需求，调整字体样式，比如颜色、大小、位置等。



>  完整引入 iconfont 图标到 HTML 的步骤

 下载字体图标文件

- 去 [iconfont 官网](https://www.iconfont.cn/) 选择需要的图标，加入购物车后下载「字体文件」压缩包。

- 解压后，将以下核心文件复制到项目的 

  ```
  fonts
  ```

   或 

  ```
  iconfont
  ```

   目录下：

  - `iconfont.css`
  - `iconfont.eot`
  - `iconfont.svg`
  - `iconfont.ttf`
  - `iconfont.woff`
  - `iconfont.woff2`

  ​

在 HTML 中引入 CSS 文件

在 `<head>` 标签内，使用 `<link>` 标签引入 `iconfont.css`：

html

预览

```
<head>
  <meta charset="UTF-8">
  <title>Iconfont 示例</title>
  <!-- 引入 iconfont 样式表 -->
  <link rel="stylesheet" href="./iconfont/iconfont.css">
</head>
```

> 注意：`href` 路径要和你项目中 `iconfont.css` 的实际位置一致。
>
> 

 在 HTML 中使用图标

通过 `<i>` 或 `<span>` 标签，加上类名 `iconfont` 和图标对应的类名即可使用：

html

预览

```
<body>
  <!-- 基本使用：假设图标类名为 icon-home -->
  <i class="iconfont icon-home"></i>

  <!-- 自定义样式：修改颜色、大小 -->
  <i class="iconfont icon-user" style="font-size: 24px; color: #333;"></i>
</body>
```

> 图标类名可以在 iconfont 官网「我的项目」中查看，或在 `iconfont.css` 文件里找到。
>
> 

使用 Unicode 方式引入

如果不想依赖 CSS 类名，也可以直接用 Unicode 字符：

html

预览

```
<style>
  .icon {
    font-family: "iconfont" !important;
    font-size: 16px;
    font-style: normal;
  }
</style>

<span class="icon">&#xe600;</span>
```

> `&#xe600;` 是图标的 Unicode 编码，同样可在官网或 `iconfont.css` 中查到。
>
> 

完整示例代码



```
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <title>Iconfont 引入示例</title>
  <link rel="stylesheet" href="./iconfont/iconfont.css">
  <style>
    /* 自定义图标样式 */
    .my-icon {
      font-size: 32px;
      color: #2f54eb;
      margin-right: 10px;
    }
  </style>
</head>
<body>
  <h1>Iconfont 图标示例</h1>
  <i class="iconfont icon-home my-icon"></i>
  <i class="iconfont icon-cart my-icon"></i>
  <i class="iconfont icon-user my-icon"></i>
</body>
</html>
```

 常见问题

- **图标不显示**：检查 `iconfont.css` 路径是否正确，字体文件是否和 CSS 在同一目录。
- **样式被覆盖**：给图标样式加 `!important`，或提高 CSS 选择器优先级。
- **兼容性**：iconfont 字体文件已兼容大部分现代浏览器和旧版浏览器。

## 精灵图

css精灵图（css sprites）是将多个小图标或图像合并到一张大图中，通过调整background-position属性来显示特定部分的图像技术

通过合理使用CSS精灵图，可以有效优化网页性能，对于复杂场景，建议结合SVG或字体图标使用

使用场景：

1. 导航菜单图标
2. 按钮操作图标
3. 复杂彩色小图标更适合精灵图

优势：

1. 减少HTTP请求，多个小图标合并为一张图片，只需一次请求。
2. 提升性能，减少网络开销，尤其适合移动端或低宽带场景。
3. 统一管理，方便维护图标集，避免文件分散。


原理：

1. 给盒子添加背景图片
2. 通过背景定位移动位置对齐
3. 注意网页坐标不同