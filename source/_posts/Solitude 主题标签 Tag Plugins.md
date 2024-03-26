---
title: 主题标签 Tag Plugins
abbrlink: e19cb4b7
date: 2023-11-6 15:37
recommend: true
categories:
  - [ 我的项目,Solitude ]
  - [ 热门 ]
tags:
  - [ Solitude ]
  - [ 精选 ]
cover: https://7.isyangs.cn/34/65ed44d710c5f-34.png
sticky: 1
comment: true
---

## 按钮 btn

{% tabs btn %}

<!-- tab 标签语法 -->

```markdown
{% btn [url],[text],[icon],[color] [style] [layout] [position] [size] %}

[url] : 链接
[text] : 按钮文字
[icon] : [可选] 图标
[color] : [可选] 按钮背景顔色(默认 style 时）
按钮字体和边框顔色(outline 时)
bg-default/bg-blue/bg-pink/bg-red/bg-purple/bg-orange/bg-green
[style] : [可选] 按钮样式 默认实心
outline/留空
[layout] : [可选] 按钮佈局 默认为 line
block/留空
[position] : [可选] 按钮位置 前提是设置了 layout 为 block 默认为左边
center/right/留空
[size] : [可选] 按钮大小
larger/留空
```

<!-- endtab -->

<!-- tab 配置参数 -->

| 参数       | 含义                                                                                   |
|----------|--------------------------------------------------------------------------------------|
| url      | 链接                                                                                   |
| text     | 按钮文字                                                                                 |
| icon     | [可选] 图标                                                                              |
| color    | [可选] 按钮背景顔色(默认 style 时）按钮字体和边框顔色(outline 时)default/blue/pink/red/purple/orange/green |
| layout   | [可选] 按钮佈局 默认为 line block/留空                                                          |
| position | [可选] 按钮位置 前提是设置了 layout 为 block 默认为左边 center/right/留空                                |
| size     | [可选] 按钮大小 larger/留空                                                                  |

<!-- endtab -->

<!-- tab 样式预览 -->

> 一组按钮

This is my website, click the btn {% btn 'https://efu.me/',Efu %}

This is my website, click the btn {% btn 'https://efu.me/',Efu,st-lightbulb-line %}

This is my website, click the btn {% btn 'https://efu.me/',Efu,,outline %}

This is my website, click the btn {% btn 'https://efu.me/',Efu,st-lightbulb-line,outline %}

This is my website, click the btn {% btn 'https://efu.me/',Efu,st-lightbulb-line,larger %}

> 调整位置或大小

{% btn 'https://efu.me/',Efu,st-lightbulb-line,block %}

{% btn 'https://efu.me/',Efu,st-lightbulb-line,block center larger %}

{% btn 'https://efu.me/',Efu,st-lightbulb-line,block right larger %}

> more than one btn in center

<span>
{% btn 'https://efu.me/',Efu, st-lightbulb-line,larger %}
{% btn 'https://efu.me/',Efu, st-lightbulb-line,bg-blue larger %}
{% btn 'https://efu.me/',Efu, st-lightbulb-line,bg-pink larger %}
{% btn 'https://efu.me/',Efu, st-lightbulb-line,bg-red larger %}
{% btn 'https://efu.me/',Efu, st-lightbulb-line,bg-purple larger %}
{% btn 'https://efu.me/',Efu, st-lightbulb-line,bg-orange larger %}
{% btn 'https://efu.me/',Efu, st-lightbulb-line,bg-green larger %}
</span>

> 居中按钮

<div align="center">
{% btn 'https://efu.me/',Efu, st-lightbulb-line,outline larger %}
{% btn 'https://efu.me/',Efu, st-lightbulb-line,outline blue larger %}
{% btn 'https://efu.me/',Efu,st-lightbulb-line,pink larger %}
{% btn 'https://efu.me/',Efu,st-lightbulb-line,red larger %}
{% btn 'https://efu.me/',Efu,st-lightbulb-line,purple larger %}
{% btn 'https://efu.me/',Efu,st-lightbulb-line,orange larger %}
{% btn 'https://efu.me/',Efu,st-lightbulb-line,green larger %}
</div>

<!-- endtab -->

<!-- tab 演示源码 -->

```markdown
> 一组按钮

This is my website, click the btn {% btn 'https://efu.me/',Efu %}
This is my website, click the btn {% btn 'https://efu.me/',Efu,st-lightbulb-line %}
This is my website, click the btn {% btn 'https://efu.me/',Efu,,outline %}
This is my website, click the btn {% btn 'https://efu.me/',Solitude,st-lightbulb-line,outline %}
This is my website, click the btn {% btn 'https://efu.me/',Solitude,st-lightbulb-line,larger %}

> 调整位置或大小

{% btn 'https://efu.me/',Efu,st-lightbulb-line,block %}
{% btn 'https://efu.me/',Efu,st-lightbulb-line,block center larger %}
{% btn 'https://efu.me/',Efu,st-lightbulb-line,block right outline larger %}

> more than one btn in center

<span>
{% btn 'https://efu.me/',Efu,st-lightbulb-line,larger %}
{% btn 'https://efu.me/',Efu,st-lightbulb-line,blue larger %}
{% btn 'https://efu.me/',Efu,st-lightbulb-line,pink larger %}
{% btn 'https://efu.me/',Efu,st-lightbulb-line,red larger %}
{% btn 'https://efu.me/',Efu,st-lightbulb-line,purple larger %}
{% btn 'https://efu.me/',Efu,st-lightbulb-line,orange larger %}
{% btn 'https://efu.me/',Efu,st-lightbulb-line,green larger %}
</span>

> 居中按钮

<div class="btn-center">
{% btn 'https://efu.me/',Efu,st-lightbulb-line,outline larger %}
{% btn 'https://efu.me/',Efu,st-lightbulb-line,outline blue larger %}
{% btn 'https://efu.me/',Efu,st-lightbulb-line,outline pink larger %}
{% btn 'https://efu.me/',Efu,st-lightbulb-line,outline red larger %}
{% btn 'https://efu.me/',Efu,st-lightbulb-line,outline purple larger %}
{% btn 'https://efu.me/',Efu,st-lightbulb-line,outline orange larger %}
{% btn 'https://efu.me/',Efu,st-lightbulb-line,outline green larger %}
</div>
```

<!-- endtab -->

{% endtabs %}

## 单张图片 image

{% tabs image %}

<!-- tab 标签语法 -->

```markdown
{% image 链接, width=宽度（可选）, height=高度（可选）, alt=描述（可选）, bg=占位颜色（可选） %}
```

<!-- endtab -->

<!-- tab 配置参数 -->

1. 图片宽度高度：width=300px, height=32px
2. 图片描述：alt=图片描述
3. 占位背景色：bg=#f2f2f2

<!-- endtab -->

<!-- tab 样式预览 -->

> 添加描述

{% image https://bu.dusays.com/2023/06/01/6478937d7de6f.webp, alt=每天下课回宿舍的路，没有什么故事。 %}

> 指定宽度

{% image https://bu.dusays.com/2023/06/01/6478937d7de6f.webp, width=400px %}

> 设置占位背景色

{% image https://bu.dusays.com/2023/06/01/6478937d7de6f.webp, width=400px, bg=#1D0C04, alt=优化不同宽度浏览的观感 %}

<!-- endtab -->

<!-- tab 演示源码 -->

```markdown
> 添加描述

{% image https://bu.dusays.com/2023/06/01/6478937d7de6f.webp, alt=每天下课回宿舍的路，没有什么故事。 %}

> 指定宽度

{% image https://bu.dusays.com/2023/06/01/6478937d7de6f.webp, width=400px %}

> 设置占位背景色

{% image https://bu.dusays.com/2023/06/01/6478937d7de6f.webp, width=400px, bg=#1D0C04, alt=优化不同宽度浏览的观感 %}
```

<!-- endtab -->

{% endtabs %}

## 行内图片 inlineimage

{% tabs inlineimage %}

<!-- tab 标签语法 -->

```markdown
{% inlineimage 图片链接, height=高度（可选） %}
```

<!-- endtab -->

<!-- tab 配置参数 -->

1. 高度：height=20px

<!-- endtab -->

<!-- tab 样式预览 -->

这是 {% inlineimage https://bu.dusays.com/2023/06/01/647895232e5d5.webp %} 一段话。

这又是 {% inlineimage https://bu.dusays.com/2022/05/19/6285328a83ca7.gif 40px %} 一段话。

<!-- endtab -->

<!-- tab 演示源码 -->

```markdown
这是 {% inlineimage https://bu.dusays.com/2023/06/01/647895232e5d5.webp %} 一段话。

这又是 {% inlineimage https://bu.dusays.com/2022/05/19/6285328a83ca7.gif, height=40px %} 一段话。
```

<!-- endtab -->

{% endtabs %}

## label 标签

{% tabs label %}

<!-- tab 标签语法 -->

```markdown
{% label text color %}
```

<!-- endtab -->

<!-- tab 配置参数 -->

| 参数    | 释义                                                             |
|-------|----------------------------------------------------------------|
| text  | 文字                                                             |
| color | 【可选】背景颜色，默认为 default，default/blue/pink/red/purple/orange/green |

<!-- endtab -->

<!-- tab 样式预览 -->

臣亮言：{% label 先帝 %}创业未半，而{% label 中道崩殂 blue %}。今天下三分，{% label 益州疲敝 pink %}，此诚{% label 危急存亡之秋 red %}也！然侍衞之臣，不懈于内；{% label 忠志之士 purple %}，忘身于外者，盖追先帝之殊遇，欲报之于陛下也。诚宜开张圣听，以光先帝遗德，恢弘志士之气；不宜妄自菲薄，引喻失义，以塞忠谏之路也。
宫中、府中，俱为一体；陟罚臧否，不宜异同。若有{% label 作奸 orange %}、{% label 犯科 green %}，及为忠善者，宜付有司，论其刑赏，以昭陛下平明之治；不宜偏私，使内外异法也。

<!-- endtab -->

<!-- tab 演示源码 -->

```markdown
臣亮言：{% label 先帝 %}创业未半，而{% label 中道崩殂 blue %}。今天下三分，{% label 益州疲敝 pink %}，此诚{% label 危急存亡之秋 red %}也！然侍衞之臣，不懈于内；{% label 忠志之士 purple %}，忘身于外者，盖追先帝之殊遇，欲报之于陛下也。诚宜开张圣听，以光先帝遗德，恢弘志士之气；不宜妄自菲薄，引喻失义，以塞忠谏之路也。
宫中、府中，俱为一体；陟罚臧否，不宜异同。若有{% label 作奸 orange %}、{% label 犯科 green %}，及为忠善者，宜付有司，论其刑赏，以昭陛下平明之治；不宜偏私，使内外异法也。
```

<!-- endtab -->

{% endtabs %}

## 直链音频 audio

{% tabs audio %}

<!-- tab 标签语法 -->

```markdown
{% audio 音频链接 %}
```

<!-- endtab -->

<!-- tab 样式预览 -->

{% audio https://npm.elemecdn.com/anzhiyu-music@1.0.4/%E9%9D%92%E8%8A%B1%E7%93%B7/%E9%9D%92%E8%8A%B1%E7%93%B7.mp3 %}

<!-- endtab -->

<!-- tab 演示源码 -->

```markdown
{% audio 音频链接 %}
```

<!-- endtab -->

{% endtabs %}

## 直链视频 video

{% tabs video %}

<!-- tab 标签语法 -->

```markdown
{% video 视频链接 %}
```

<!-- endtab -->

<!-- tab 配置参数 -->

1. 对其方向：left, center, right
2. 列数：逗号后面直接写列数，支持 1 ～ 4 列。

<!-- endtab -->

<!-- tab 样式预览 -->

> 默认

![](https://7.isyangs.cn/34/65f7f0ae6af48-34.png)

> 50% 宽度

![](https://7.isyangs.cn/34/65f7f15b0341c-34.png)

> 25 %

![](https://7.isyangs.cn/34/65f7f12ebef8c-34.png)

<!-- endtab -->

<!-- tab 演示源码 -->

```markdown
> 默认

{% video https://github.com/volantis-x/volantis-docs/releases/download/assets/IMG_0341.mov %}

> 50% 宽度

{% videos, 2 %}
{% video https://github.com/volantis-x/volantis-docs/releases/download/assets/IMG_0341.mov %}
{% video https://github.com/volantis-x/volantis-docs/releases/download/assets/IMG_0341.mov %}
{% video https://github.com/volantis-x/volantis-docs/releases/download/assets/IMG_0341.mov %}
{% video https://github.com/volantis-x/volantis-docs/releases/download/assets/IMG_0341.mov %}
{% endvideos %}

> 25 %

{% videos, 4 %}
{% video https://github.com/volantis-x/volantis-docs/releases/download/assets/IMG_0341.mov %}
{% video https://github.com/volantis-x/volantis-docs/releases/download/assets/IMG_0341.mov %}
{% video https://github.com/volantis-x/volantis-docs/releases/download/assets/IMG_0341.mov %}
{% video https://github.com/volantis-x/volantis-docs/releases/download/assets/IMG_0341.mov %}
{% video https://github.com/volantis-x/volantis-docs/releases/download/assets/IMG_0341.mov %}
{% video https://github.com/volantis-x/volantis-docs/releases/download/assets/IMG_0341.mov %}
{% video https://github.com/volantis-x/volantis-docs/releases/download/assets/IMG_0341.mov %}
{% video https://github.com/volantis-x/volantis-docs/releases/download/assets/IMG_0341.mov %}
{% endvideos %}
```

<!-- endtab -->

{% endtabs %}

## 段落文本 p

{% tabs P %}

<!-- tab 标签语法 -->

```markdown
{% p 样式参数(参数以空格划分), 文本内容 %}
```

<!-- endtab -->

<!-- tab 配置参数 -->

1. 字体: logo, code
2. 颜色: {% span red, red %},{% span yellow, yellow %},{% span green, green %},{% span cyan, cyan %},{% span blue,
   blue %},{% span gray, gray %}
3. 大小: small, h4, h3, h2, h1, large, huge, ultra
4. 对齐方向: left, center, right

<!-- endtab -->

<!-- tab 样式预览 -->

{% p red left, red left %}

{% p yellow center, yellow center %}

{% p green right, green right %}

{% p center h1, center h1 %}

{% p center ultra, center ultra %}

<!-- endtab -->

<!-- tab 演示源码 -->

```markdown

{% p red left, red left %}

{% p yellow center, yellow center %}

{% p green right, green right %}

{% p center h1, center h1 %}

{% p center ultra, center ultra %}
```

<!-- endtab -->

{% endtabs %}

## Note (Bootstrap Callout)

{% tabs Note %}

> 不支持自定义图标，如有需求请自行修改，需求人数多可考虑主题内嵌。

<!-- tab 标签语法 -->

```markdown
{% note [class] %}
Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aperiam, libero.
{% endnote %}
```

<!-- endtab -->

<!-- tab 配置参数 -->

| 参数    | 含义  |
|-------|-----|
| class | 显示值 |

显示值：（中间空格）

- 配色
    * default / primary / success / info / warning / danger
- 样式
    * simple / modern / flat / disabled
- 图标
    * noicon

<!-- endtab -->

<!-- tab 样式预览 -->

> 默认样式

{% note simple %}
Demo 1 - default
{% endnote %}

> Simple 样式

{% note default simple %}
Demo 1 - default
{% endnote %}

{% note primary simple %}
Demo 2 - primary
{% endnote %}

{% note success simple %}
Demo 3 - success
{% endnote %}

{% note info simple %}
Demo 4 - info
{% endnote %}

{% note warning simple %}
Demo 5 - warning
{% endnote %}

{% note danger simple %}
Demo 6 - danger
{% endnote %}

> Modern 样式

{% note default modern %}
Demo 1 - default
{% endnote %}

{% note primary modern %}
Demo 2 - primary
{% endnote %}

{% note success modern %}
Demo 3 - success
{% endnote %}

{% note info modern %}
Demo 4 - info
{% endnote %}

{% note warning modern %}
Demo 5 - warning
{% endnote %}

{% note danger modern %}
Demo 6 - danger
{% endnote %}

> Flat 样式

{% note default flat %}
Demo 1 - default
{% endnote %}

{% note primary flat %}
Demo 2 - primary
{% endnote %}

{% note success flat %}
Demo 3 - success
{% endnote %}

{% note info flat %}
Demo 4 - info
{% endnote %}

{% note warning flat %}
Demo 5 - warning
{% endnote %}

{% note danger flat %}
Demo 6 - danger
{% endnote %}

> Disabled 样式

{% note default disabled %}
Demo 1 - default
{% endnote %}

{% note primary disabled %}
Demo 2 - primary
{% endnote %}

{% note success disabled %}
Demo 3 - success
{% endnote %}

{% note info disabled %}
Demo 4 - info
{% endnote %}

{% note warning disabled %}
Demo 5 - warning
{% endnote %}

{% note danger disabled %}
Demo 6 - danger
{% endnote %}

<!-- endtab -->

<!-- tab 演示源码 -->

```markdown
默认样式：
{% note default %}
Demo 1 - default
{% endnote %}

1. Simple 样式
   {% note default simple %}
   Demo 1 - default
   {% endnote %}

{% note primary simple %}
Demo 2 - primary
{% endnote %}

{% note success simple %}
Demo 3 - success
{% endnote %}

{% note info simple %}
Demo 4 - info
{% endnote %}

{% note warning simple %}
Demo 5 - warning
{% endnote %}

{% note danger simple %}
Demo 6 - danger
{% endnote %}

2. Modern 样式
   {% note default modern %}
   Demo 1 - default
   {% endnote %}

{% note primary modern %}
Demo 2 - primary
{% endnote %}

{% note success modern %}
Demo 3 - success
{% endnote %}

{% note info modern %}
Demo 4 - info
{% endnote %}

{% note warning modern %}
Demo 5 - warning
{% endnote %}

{% note danger modern %}
Demo 6 - danger
{% endnote %}

3. Flat 样式
   {% note default flat %}
   Demo 1 - default
   {% endnote %}

{% note primary flat %}
Demo 2 - primary
{% endnote %}

{% note success flat %}
Demo 3 - success
{% endnote %}

{% note info flat %}
Demo 4 - info
{% endnote %}

{% note warning flat %}
Demo 5 - warning
{% endnote %}

{% note danger flat %}
Demo 6 - danger
{% endnote %}

3. Disabled 样式
   {% note default disabled %}
   Demo 1 - default
   {% endnote %}

{% note primary disabled %}
Demo 2 - primary
{% endnote %}

{% note success disabled %}
Demo 3 - success
{% endnote %}

{% note info disabled %}
Demo 4 - info
{% endnote %}

{% note warning disabled %}
Demo 5 - warning
{% endnote %}

{% note danger disabled %}
Demo 6 - danger
{% endnote %}
```

<!-- endtab -->

{% endtabs %}

## 分栏 tabs

> 分栏支持内置codesign图标，如果开启了 customicon 则可以使用自定义的图标，否则只能使用默内置codesign图标

{% tabs 分栏 %}

<!-- tab 标签语法 -->

```markdown
{% tabs Unique name, [index] %}

<!-- tab [Tab caption] [@icon] -->

Any content (support inline tags too).

<!-- endtab -->

{% endtabs %}
```

<!-- endtab -->

<!-- tab 配置参数 -->

1. Unique name：不带逗号的选项卡块标记的唯一名称。
   1. 将在 #id 中用作每个选项卡及其索引号的前缀。 
   2. 如果名称中有空格，则对于生成 #id 所有空格都将替换为破折号。 
   3. 仅帖子/页面的当前网址必须是唯一的！
2. [index]：活动选项卡的索引号。 
   1. 如果未指定，将选择第一个选项卡 （1）。 
   2. 如果 index 为 -1，则不选择任何选项卡。这将是剧透。 
   3. 可选参数。
3. [Tab caption]：当前选项卡的标题。
   1. 如果未指定标题，则带有选项卡索引后缀的唯一名称将用作选项卡的标题。 
   2. 如果未指定标题，但指定了图标，则标题将为空。 
   3. 可选参数。
4. [@icon]：图标名称（全名，例如“solitude st-logo”） 
   1. 可以指定有或没有空格;例如，“Tab caption @icon”类似于“Tab caption@icon”。 
   2. 可选参数。

<!-- endtab -->

<!-- tab 样式预览 -->

{% note primary flat %}
Demo 1 - 预设选择第一个【默认】
{% endnote %}

{% subtabs Demo1 %}
<!-- tab test1 -->
This is Tab 1.
<!-- endtab-->
<!-- tab test2 -->
This is Tab 2.
<!-- endtab-->
<!-- tab test3 -->
This is Tab 3.
<!-- endtab-->
{% endsubtabs %}

{% note primary flat %}
Demo 2 - 没有预设值
{% endnote %}

{% subtabs Demo2 %}
<!-- tab -->
This is Tab 1.
<!-- endtab-->
<!-- tab -->
This is Tab 2.
<!-- endtab-->
<!-- tab -->
This is Tab 3.
<!-- endtab-->
{% endsubtabs %}

{% note primary flat %}
Demo 3 - 自定义Tab名 + icon + Tab名和icon
{% endnote %}

{% subtabs Demo3 %}
<!-- tab test1  -->
This is Tab 1.
<!-- endtab-->
<!-- tab @sco-disc-fill -->
This is Tab 2.
<!-- endtab-->
<!-- tab 音乐 @sco-disc-fill -->
This is Tab 3.
<!-- endtab-->
{% endsubtabs %}

<!-- endtab -->

<!-- tab 演示源码 -->

{% note primary flat %}
Demo 1 - 预设选择第一个【默认】
{% endnote %}

```markdown

{% subtabs Demo1 %}
<!-- tab test1 -->
This is Tab 1.
<!-- endtab-->
<!-- tab test2 -->
This is Tab 2.
<!-- endtab-->
<!-- tab test3 -->
This is Tab 3.
<!-- endtab-->
{% endsubtabs %}
```

{% note primary flat %}
Demo 2 - 没有预设值
{% endnote %}

```markdown
{% subtabs Demo2 %}
<!-- tab -->
This is Tab 1.
<!-- endtab-->
<!-- tab -->
This is Tab 2.
<!-- endtab-->
<!-- tab -->
This is Tab 3.
<!-- endtab-->
{% endsubtabs %}

```

{% note primary flat %}
Demo 3 - 自定义Tab名 + icon + Tab名和icon
{% endnote %}

```markdown
{% subtabs Demo3 %}
<!-- tab test1  -->
This is Tab 1.
<!-- endtab-->
<!-- tab @sco-disc-fill -->
This is Tab 2.
<!-- endtab-->
<!-- tab 音乐 @sco-disc-fill -->
This is Tab 3.
<!-- endtab-->
{% endsubtabs %}
```

<!-- endtab -->

{% endtabs %}

## 时间轴 Timelne

{% tabs 时间轴 %}

<!-- tab 标签语法 -->

```markdown
{% timeline title %}

{% timenode title %}

xxxx

{% endtimenode %}

{% timenode title %}

xxxx

{% endtimenode %}

{% endtimeline %}
```

<!-- endtab -->

<!-- tab 参数配置 -->

| 参数    | 含义   |
|-------|------|
| title | 节点名称 |
| xxxx  | 内容区  |

<!-- endtab -->

<!-- tab 样式预览 -->

{% timeline %}

{% timenode 8 %}

- 你好
- 你好

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Distinctio dolores eaque est ex voluptatum. Consequuntur
eligendi esse fugit quasi ut.

{% endtimenode %}

{% timenode 9 %}

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ad amet animi assumenda atque consequatur, doloribus eligendi
est excepturi facere molestias nam, omnis perspiciatis quas, repellendus sit. Ipsum, rem, velit?

{% endtimenode %}

{% endtimeline %}

<!-- endtab -->

<!-- tab 演示源码 -->

```markdown
{% timeline %}

{% timenode 8 %}

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Distinctio dolores eaque est ex voluptatum. Consequuntur
eligendi esse fugit quasi ut.

{% endtimenode %}

{% timenode 9 %}

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ad amet animi assumenda atque consequatur, doloribus eligendi
est excepturi facere molestias nam, omnis perspiciatis quas, repellendus sit. Ipsum, rem, velit?

{% endtimenode %}

{% endtimeline %}
```

<!-- endtab -->

{% endtabs %}

## 外链 link

{% tabs 外链 %}

<!-- tab 标签语法 -->

```markdown
{% link [title],[subtitle],[link] %}
```

<!-- endtab -->

<!-- tab 参数配置 -->

| 参数       | 含义   |
|----------|------|
| title    | 标题   |
| subtitle | 简介   |
| link     | 跳转链接 |

<!-- endtab -->

<!-- tab 样式预览 -->
{% link Solitude,官方文档地址,https://solitude-docs.efu.me/ %}

{% link 知乎,有问题，就会有答案,https://www.zhihu.com/ %}

{% link Efu,作者博客,https://efu.me/ %}

<!-- endtab -->

<!-- tab 演示源码 -->

```markdown
{% link Solitude,官方文档地址,https://solitude-docs.efu.me/ %}

{% link 知乎,有问题，就会有答案,https://www.zhihu.com/ %}
```

<!-- endtab -->

{% endtabs %}

## 折叠块 fold

{% tabs 折叠块 %}

<!-- tab 标签语法 -->

```markdown
{% fold title open %}

{% endfold %}
```

<!-- endtab -->

<!-- tab 配置参数 -->

| 参数    | 含义              |
|-------|-----------------|
| title | 标题（可选）          |
| oepn  | 是否打开（可选）不填默认不打开 |

<!-- endtab -->

<!-- tab 演示预览 -->

{% note primary flat %}
Demo 1 - title
{% endnote %}

{% fold Demo1 %}

{% endfold %}

{% note primary flat %}
Demo 2 - title + open
{% endnote %}

{% fold Demo2 open %}

{% endfold %}

<!-- endtab -->

<!-- tab 演示源码 -->

{% note primary flat %}
Demo 1 - title
{% endnote %}

```markdown
{% fold Demo1 %}

{% endfold %}
```

{% note primary flat %}
Demo 2 - title + open
{% endnote %}

```markdown
{% fold Demo2 open %}

{% endfold %}
```

<!-- endtab -->

{% endtabs %}

## bvideo 视频播放

{% tabs bvideo视频播放 %}

<!-- tab 标签语法 -->

```markdown
{% bvideo [id] [time] %}
```

<!-- endtab -->

<!-- tab 配置参数 -->

| 参数  | 含义                          |
|-----|-----------------------------|
| url | bvid（例如视频链接后的：BV1nj411i7Ja） |

<!-- endtab -->

<!-- tab 演示预览 -->

{% bvideo BV1nj411i7Ja %}

<!-- endtab -->

<!-- tab 演示源码 -->

```markdown
{% bvideo BV1nj411i7Ja %}
```

<!-- endtab -->

{% endtabs %}

## 复选列表 checkbox

{% tabs checkbox %}
<!-- tab 标签语法 -->

```markdown
{% checkbox 样式参数（可选）, 文本内容 %}
```

<!-- endtab -->

<!-- tab 配置参数 -->

1. 样式: plus, minus, times
2. 颜色: red,yellow,green,cyan,blue,gray
3. 选中状态: checked

<!-- endtab -->

<!-- tab 演示预览 -->

{% checkbox 纯文本测试 %}
{% checkbox checked, 支持简单的 [markdown](https://guides.github.com/features/mastering-markdown/) 语法 %}
{% checkbox red, 支持自定义颜色 %}
{% checkbox green checked, 绿色 + 默认选中 %}
{% checkbox yellow checked, 黄色 + 默认选中 %}
{% checkbox cyan checked, 青色 + 默认选中 %}
{% checkbox blue checked, 蓝色 + 默认选中 %}
{% checkbox plus green checked, 增加 %}
{% checkbox minus yellow checked, 减少 %}
{% checkbox times red checked, 叉 %}

<!-- endtab -->

<!-- tab 演示源码 -->

```markdown
{% checkbox 纯文本测试 %}
{% checkbox checked, 支持简单的 [markdown](https://guides.github.com/features/mastering-markdown/) 语法 %}
{% checkbox red, 支持自定义颜色 %}
{% checkbox green checked, 绿色 + 默认选中 %}
{% checkbox yellow checked, 黄色 + 默认选中 %}
{% checkbox cyan checked, 青色 + 默认选中 %}
{% checkbox blue checked, 蓝色 + 默认选中 %}
{% checkbox plus green checked, 增加 %}
{% checkbox minus yellow checked, 减少 %}
{% checkbox times red checked, 叉 %}
```

<!-- endtab -->

{% endtabs %}

## mermaid 图

{% note info simple %}

使用`mermaid标签`可以绘制Flowchart（流程图）、Sequence diagram（时序图 ）、Class Diagram（类别图）、State Diagram（状态图）、Gantt（甘特图）和Pie Chart（圆形图），具体可以查看[mermaid文档](https://mermaid.js.org/#/)

{% endnote %}

{% note danger simple %}

如果使用了 gulp 一定要关闭使用过 mermaid 的页面，具体看[文档详情](https://solitude-docs.efu.me/high-configuration/advanced#gulp)

{% endnote %}

* 打开主题配置文件中的开关

```yaml
mermaid: true
```

{% tabs mermaid图 %}

<!-- tab 标签语法 -->

```markdown
{% mermaid %}
graph TD:
    A-->B;
    A-->C;
    B-->D;
    C-->D;
{% endmermaid %}
```

<!-- endtab -->

<!-- tab 演示预览 -->

![](https://7.isyangs.cn/34/65f7fd27eb75e-34.png)

<!-- endtab -->

<!-- tab 演示源码 -->

```markdown
{% mermaid %}
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
{% endmermaid %}
```

<!-- endtab -->

{% endtabs %}

## gallery 图库

{% tabs 图库 %}

<!-- tab 标签语法 -->

```markdown
{% gallery 图库 图库简介 链接 图片 %}
```

<!-- endtab -->

<!-- tab 演示预览 -->

> 相册

<div style="display: flex; justify-content: center;gap: 10px">

{% galleryGroup 图库 图库简介 链接 https://7.isyangs.cn/34/65ed523eec48d-34.jpeg %}
{% galleryGroup 图库 图库简介 链接 https://7.isyangs.cn/34/65ed523eec48d-34.jpeg %}

</div>

<div style="display: flex; justify-content: center;gap: 10px">

{% galleryGroup 图库 图库简介 链接 https://7.isyangs.cn/34/65ed523eec48d-34.jpeg %}
{% galleryGroup 图库 图库简介 链接 https://7.isyangs.cn/34/65ed523eec48d-34.jpeg %}

</div>

> 相册内容页

<!-- endtab -->

<!-- tab 演示源码 -->

```markdown
{% mermaid %}
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
{% endmermaid %}
```

<!-- endtab -->

{% endtabs %}