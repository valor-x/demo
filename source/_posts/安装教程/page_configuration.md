---
title: Solitude 安装文档(二) 页面配置
categories:
  - Docs
tags:
  - Docs
abbrlink: 2db7d40c
date: 2024-02-16 01:00:00
cover: https://bu.dusays.com/2024/02/16/65cf1a15b083b.png
---

## Front Matter

> Front-matter 是 markdown 文件最上方以 --- 分隔的区域，用于指定页面的特殊值。

{% tabs Front-matter %}

<!-- tab Post Front Matter -->

```markdown
---
title:
date:
type:
comment:
cover:
katex:
type:
reprint:
locate:
---
```

<!-- endtab -->

<!-- tab Page Front Matter -->

```markdown
---
title:
date:
updated:
type:
comment:
desc:
cover:
katex:
aside:
type:
---
```

<!-- endtab -->

<!-- tab 即刻、工具箱、我的装备、豆瓣页（音乐、图书、游戏）-->

```markdown
---
leftend:
rightend:
rightbtn:
rightbtn:
rightbtnlink:
---
```

<!-- endtab -->

{% endtabs %}

| 属性           | 值类型      | 解释                           |
|--------------|----------|------------------------------|
| title        | string   | 【必需】页面标题                     |
| date         | datetime | 【必需】页面创建日期                   |
| type         | string   | 【必需】关于、友情链接、朋友圈、即刻、工具箱页面需要配置 |
| updated      | datetime | 【可选】页面更新日期                   |
| desc         | string   | 【可选】页面描述                     |
| aside        | boolean  | 【可选】是否开启侧边栏（默认true）          |
| comment      | boolean  | 【可选】显示页面评论模块(默认 true)        |
| cover        | string   | 【可选】页面顶部图片URL                |
| reprint      | boolean  | 【可选】版权（默认为原创）为true时为转载       |
| katex        | boolean  | 【可选】显示 katex(默认 false)       |
| locate       | string   | 【可选】文章创作地点                   |
| leftend      | string   | 【可选】banner底部左侧文字             |
| rightend     | string   | 【可选】banner底部右侧文字             |
| rightbtn     | string   | 【可选】banner底部右侧按钮文字           |
| rightbtnlink | string   | 【可选】banner底部右侧按钮跳转链接         |

## 标签页和分类页

> 主题已内置标签页和分类页，无需额外配置，只需在主题配置文件中开启。

```yaml
# 页面页默认设置
page:
  error: true  # 404页面
  tags: true # 标签页
  categories: true # 分类页
  default: # 默认值
    cover: 
      - /img/default.png # 默认图片
```

## 404页面

> 主题内置了一个简单的 404 页面，可在设置中开启 本地预览时，访问出错的网站是不会跳到 404 页面的。

![404页面](https://bu.dusays.com/2024/03/01/65e19dcea01c8.png)
