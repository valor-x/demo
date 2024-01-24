---
title: 数学公式
recommend: true
categories:
  - [ 我的项目,Solitude ]
tags:
  - [ Solitude ]
  - [ Latex ]
abbrlink: b1d1f75b
katex: true
cover: https://bu.dusays.com/2024/01/24/65b11247a9769.png
---

> 本文介绍了如何在Solitude主题下使用数学公式。

## 一、Katex

KaTeX是一个快速、易于使用的JavaScript库，用于在网络上进行TeX数学渲染。

以下是 KaTeX 的一些主要特性：

1. **速度**：KaTeX 旨在比其他类似的库（如 MathJax）更快。这是因为 KaTeX 在服务器端渲染数学公式，然后将结果作为纯 HTML 和 CSS 发送到客户端，而不是在客户端进行渲染。
2. **易于使用**：KaTeX 可以很容易地集成到你的网站或应用中。你只需要在你的 HTML 中包含 KaTeX 的 JavaScript 和 CSS 文件，然后使用特定的标记来写数学公式。
3. **高质量的渲染**：KaTeX 生成的数学公式看起来非常清晰和专业。它支持许多 LaTeX 的数学符号和命令，因此你可以写出非常复杂的数学公式。
4. **无需依赖**：KaTeX 不需要任何外部库或插件就可以工作，这使得它在许多环境中都非常方便使用。
5. **可访问性**：KaTeX 生成的公式支持屏幕阅读器，这对于视觉障碍的用户来说非常有用。

KaTeX 是一个非常强大的工具，无论你是在创建一个需要显示复杂数学公式的教育网站，还是在开发一个需要处理数学输入的应用，KaTeX 都是一个很好的选择。

### 使用Katex

1. 更换`markdown-it`渲染器
    ```shell
    npm un hexo-renderer-marked --save # 卸载hexo-marked
    npm un hexo-renderer-kramed --save # 卸载hexo-kramed
    npm i hexo-renderer-markdown-it --save # 安装hexo-markdown-it
    npm install katex @renbaoshuo/markdown-it-katex # 安装katex扩展
    ```
2. 根目录配置文件`_config.yml`中添加如下配置：
    ```yaml
    markdown:
      plugins:
        - '@renbaoshuo/markdown-it-katex' # katex扩展
      anchors:
        permalink: true # 是否显示标题的锚点
        permalinkClass: 'headerlink' # 锚点的class
    ```
3. 在Solitude主题下，使用Katex非常简单，只需要在文章的头部添加`katex: true`即可，如下所示：（Page中也能使用Katex）
   ```markdown
   ---
   katex: true
   ---
   ```
4. 在文章中使用Katex，只需要使用`$$`包裹公式即可，如下所示：
   ```markdown
    $$
    \begin{aligned}
    \frac{\partial u}{\partial t} &= \frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} \\
    \frac{\partial v}{\partial t} &= \frac{\partial^2 v}{\partial x^2} + \frac{\partial^2 v}{\partial y^2}
    \end{aligned}
    $$
    ```
    效果如下所示：
   $$
   \begin{aligned}
   \frac{\partial u}{\partial t} &= \frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} \\
   \frac{\partial v}{\partial t} &= \frac{\partial^2 v}{\partial x^2} + \frac{\partial^2 v}{\partial y^2}
   \end{aligned}
   $$

## 二、MathJax
   暂未支持...（过于臃肿，后续可能会考虑增加）