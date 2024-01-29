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
cover: https://bu.dusays.com/2024/01/24/65b11236a3dd2.png
sticky: 1
---

{% note simple primary %}
`Solitude 主题` Plugin Tags 部分移植来自店长的 [hexo-butterfly-tag-plugins-plus](https://www.npmjs.com/package/hexo-butterfly-tag-plugins-plus)，转载请注明出处。
使用方法和配置项基本相同

{% endnote %}

## 卡片 card

{% tabs card %}

<!-- tab 标签语法 -->

```markdown
{% card icon,color,title %}
content
{% endcard %}
```

<!-- endtab -->

<!-- tab 配置参数 -->

| 参数    | 含义                                |
|-------|-----------------------------------|
| color | red,green,blue,yellow,purple,cyan |
| icon  | 图标, no-icon                       |
| title | 标题                                |

<!-- endtab -->

<!-- tab 样式预览 -->

{% card no-icon,green,title %}

lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusamus, accusantium ad adipisci alias

{% endcard %}

{% card sco-circle-check-solid,green,title %}

lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusamus, accusantium ad adipisci alias

{% endcard %}

{% card sco-circle-exclamation-solid,red,title %}

lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusamus, accusantium ad adipisci alias

{% endcard %}

<!-- endtab -->

<!-- tab 演示源码 -->

```markdown
{% card no-icon,green,title %}

lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusamus, accusantium ad adipisci alias

{% endcard %}

{% card sco-circle-check-solid,green,title %}

lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusamus, accusantium ad adipisci alias

{% endcard %}

{% card sco-circle-exclamation-solid,red,title %}

lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusamus, accusantium ad adipisci alias

{% endcard %}
```

<!-- endtab -->

{% endtabs %}

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

This is my website, click the button {% btn 'https://blog.wzsco.top/',Solitude %}
This is my website, click the button {% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold %}
This is my website, click the button {% btn 'https://blog.wzsco.top/',Solitude,,outline %}
This is my website, click the button {% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,outline %}
This is my website, click the button {% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,larger %}

> 调整位置或大小

{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,block %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,block center larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,block right larger %}

> more than one button in center

<span>
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,bg-blue larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,bg-pink larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,bg-red larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,bg-purple larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,bg-orange larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,bg-green larger %}
</span>

> 居中按钮

<div class="btn-center">
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,outline larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,outline blue larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,outline pink larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,outline red larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,outline purple larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,outline orange larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,outline green larger %}
</div>

<!-- endtab -->

<!-- tab 演示源码 -->

```markdown
> 一组按钮

This is my website, click the button {% btn 'https://blog.wzsco.top/',Solitude %}
This is my website, click the button {% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold %}
This is my website, click the button {% btn 'https://blog.wzsco.top/',Solitude,,outline %}
This is my website, click the button {% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,outline %}
This is my website, click the button {% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,larger %}

> 调整位置或大小

{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,block %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,block center larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,block right outline larger %}

> more than one button in center

<span>
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,blue larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,pink larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,red larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,purple larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,orange larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,green larger %}
</span>

> 居中按钮

<div class="btn-center">
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,outline larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,outline blue larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,outline pink larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,outline red larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,outline purple larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,outline orange larger %}
{% btn 'https://blog.wzsco.top/',Solitude,scoicon sco-arrow-right-bold,outline green larger %}
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

{% label text red %}

<!-- endtab -->

<!-- tab 演示源码 -->

```markdown
{% label text red %}
```

<!-- endtab -->

{% endtabs %}

## 单选列表 radio

{% tabs radio %}

<!-- tab 标签语法 -->

```markdown
{% radio 样式参数（可选）, 文本（支持简单md） %}
```

<!-- endtab -->

<!-- tab 配置参数 -->

1. 颜色: red,yellow,green,cyan,blue,gray
2. 选中状态: checked

<!-- endtab -->

<!-- tab 样式预览 -->

{% radio 纯文本测试 %}
{% radio checked, 支持简单的 [markdown](https://guides.github.com/features/mastering-markdown/) 语法 %}
{% radio red, 支持自定义颜色 %}
{% radio green, 绿色 %}
{% radio yellow, 黄色 %}
{% radio cyan, 青色 %}
{% radio blue, 蓝色 %}

<!-- endtab -->

<!-- tab 演示源码 -->

```markdown
{% radio 纯文本测试 %}
{% radio checked, 支持简单的 [markdown](https://guides.github.com/features/mastering-markdown/) 语法 %}
{% radio red, 支持自定义颜色 %}
{% radio green, 绿色 %}
{% radio yellow, 黄色 %}
{% radio cyan, 青色 %}
{% radio blue, 蓝色 %}
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

{% audio 音频链接 %}

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

{% video 视频链接 %}

<!-- endtab -->

<!-- tab 演示源码 -->

```markdown

> 默认

{% video 视频链接 %}


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

1. Unique name :
    - 选项卡块标签的唯一名称，不带逗号。
    - 将在#id 中用作每个标签及其索引号的前缀。
    - 如果名称中包含空格，则对于生成#id，所有空格将由破折号代替。
    - 仅当前帖子/页面的 URL 必须是唯一的！

2. [Tab caption]:
    - 当前选项卡的标题。
    - 如果未指定标题，则带有制表符索引后缀的唯一名称将用作制表符的标题。
    - 如果未指定标题，但指定了图标，则标题将为空。
    - 可选参数。
3. [@icon]:
    - FontAwesome 图标名称（全名，看起来像“ fas fa-font”）
    - 可以指定带空格或不带空格；
    - 例如’Tab caption @icon’ 和 ‘Tab caption@icon’.
    - 可选参数。

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
{% link [title] [subtitle] [link] %}
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
{% link Solitude 官方文档地址 https://docs.wzsco.top/ %}

{% link 知乎 有问题，就会有答案 https://www.zhihu.com/ %}

<!-- endtab -->

<!-- tab 演示源码 -->

```markdown
{% link Solitude 官方文档地址 https://docs.wzsco.top/ %}

{% link 知乎 有问题，就会有答案 https://www.zhihu.com/ %}
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

## bilibili 视频播放

{% tabs bilibili视频播放 %}

<!-- tab 标签语法 -->

```markdown
{% bilibili [id] [time] %}
```

<!-- endtab -->

<!-- tab 配置参数 -->

| 参数  | 含义                                                                                              |
|-----|-------------------------------------------------------------------------------------------------|
| url | 视频嵌入链接（例如：//player.bilibili.com/player.html?aid=450061422&bvid=BV1nj411i7Ja&cid=1310680043&p=1） |

<!-- endtab -->

<!-- tab 演示预览 -->

{% bilibili //player.bilibili.com/player.html?aid=450061422&bvid=BV1nj411i7Ja&cid=1310680043&p=1 %}

<!-- endtab -->

<!-- tab 演示源码 -->

```markdown
{% bilibili //player.bilibili.com/player.html?aid=450061422&bvid=BV1nj411i7Ja&cid=1310680043&p=1 %}
```

<!-- endtab -->

{% endtabs %}