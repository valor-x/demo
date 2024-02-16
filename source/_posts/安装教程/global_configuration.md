---
title: Solitude 安装文档(三) 基本配置
categories:
  - Docs
tags:
  - Docs
abbrlink: 54a18de0
date: 2024-02-16 02:00:00
cover: https://bu.dusays.com/2024/02/16/65cf1a82648b3.png
---

## 网站资料

修改网站各种资料，例如标题、副标题和邮箱等个人资料。

**Hexo 配置文件**: `_config.yml`

```yaml
title: 王卓Sco  # 博客标题
subtitle: '宁静致远，热爱生活。'  # 博客子标题
description: '一个平凡但不拘于世的少年' # 博客简介
keywords: '王卓Sco,Sco,Solitude'  # 博客关键词
author: 王卓Sco # 博主名称
language: zh-CN # 语言
timezone: 'Asia/Shanghai' # 时区（请自行查询）
```

**主题配置文件**: `_config.solitude.yml`

```yaml
# 站点设置
# site settings
site:
  # 顶部导航栏logo区域
  # Logo area in the top navigation bar
  name:
    # 显示类型 （i_class/text/img）
    # Display type (i_class/text/img)
    class: text
    # 具体内容 例如：scoicon sco-logo / 王卓Sco / https://p.sondy.top/logo.png
    # Specific content, for example: scoicon sco-logo / 王卓Sco / https://p.sondy.top/logo.png
    custom: Solitude
  # 网页icon
  # Web icon
  siteIcon: https://bu.dusays.com/2023/11/08/654af68b25bb8.jpg
  # 页脚的Logo、加载动画默认的logo
  # Logo in the footer, default logo for loading animation
  icon: https://bu.dusays.com/2023/11/08/654af68b25bb8.jpg
```

## 导航菜单

### 左侧

**主题配置文件**: `_config.solitude.yml`

```yaml
#导航栏左侧
# left
left:
  # 是否开启左侧导航栏
  # Whether to enable the left navigation bar
  enable: false
  # 导航栏显示的内容
  # Content displayed in the navigation bar
  menu:
     # 显示分类名
     # Display category name
     项目:
       # 显示子类
       # Display subcategories
       Solitude:
         # 显示的图标
         # Displayed icon
         icon: https://bu.dusays.com/2023/11/08/654af68b25bb8.jpg
         # 点击的跳转链接
         # Click the jump link
         url: https://github.com/DuoSco/Hexo-Theme-solitude
```

### 中心

**主题配置文件**: `_config.solitude.yml`

```yaml
# 导航栏内容
# Navigation bar content
# tip：此部分内容是顶部导航栏中间菜单区域
# tip: This part of the content is the menu area in the middle of the top navigation bar
menu:
  # 显示的大分类名称
  # Displayed category name
  文库:
    # 点击跳转链接
    # Click the jump link
    # tip：如果没有子类就填跳转链接，例如：/archives，否则填false
    # tip: If there is no subcategory, fill in the jump link, for example: /archives, otherwise fill in false
    url: false
    # 子类数组
    # Subcategory array
    child:
      # 子类名称
      # Subcategory name
      文章列表:
        # 点击跳转链接
        # Click the jump link
        url: /archives/
        # 子类名称左侧图标
        # Subcategory name left icon
        icon: sco-folder-fill
      全部分类:
        url: /categories/
        icon: sco-checkbox-multiple-blank-fill
      全部标签:
        url: /tags/
        icon: sco-price-tag-fill
  友链:
    url: false
    child:
      友情链接:
        url: /links/
        icon: sco-group-fill
      宝藏博主:
        url: javascript:travelling()
        icon: sco-gift-fill
  我的:
    url: false
    child:
      装备:
        url: /equipment/
        icon: sco-laptop-line
      工具箱:
        url: /tlink/
        icon: sco-tools-fill
  关于:
    url: false
    child:
      关于本站:
        url: /about/
        icon: sco-contacts-fill
```

### 右侧
```yaml
# 导航栏右侧按钮
# Button on the right side of the navigation bar
# tip：只需填写true和false即可
# tip: Just fill in true and false
right:
  random: false        # 随机文章跳转 true：开启 / false：关闭 : random post jump true: on / false: off
  console: false       #控制台 true：开启 / false：关闭 : console true: on / false: off
  # 从左至右
  # From left to right
  custom:
    - name: 开往 - 友链接力 # 显示文字 / Displayed text
      url: https://www.travellings.cn/go.html # 跳转链接 / Jump link
      icon: sco-train-line # 图标 / Icon
      onclick:  # 点击事件 / Click event
      id: travellings_button # id

```

## 首页顶部

```yaml
# 首页顶部样式
# Home top style
hometop:
  # 首页顶部瀑布技能点、右侧文章推荐、左侧下部分三大分类
  # Home top waterfall skill points, right article recommendation, left lower part of the three major categories
  banner:
    # 是否开启显示，不开启则顶部只会显示即刻mini（需配置）
    # Whether to enable display, do not enable the top will only display the mini immediately (need to configure)
    enable: false # 是否打开顶部banner / Whether to open the top banner
    # 左上角显示大文字
    # Large text displayed in the upper left corner
    # tip：可使用html标签
    # tip: html tags can be used
    title: 宁静致远<br>热爱生活
    # 左上角显示小文字
    # Small text displayed in the upper left corner
    url: Hexo-Theme-Solitude
    # 轮播icon
    # Carousel icon
    icon:
      # 名字 / Name
      HTML:
        # 图片 / Image
        img: https://npm.elemecdn.com/wleelw-blog-abs@1.0.0/img/icon/HTML.png
        # 背景色 / Background color
        color: '#e9572b'
      JS:
        img: https://npm.elemecdn.com/wleelw-blog-abs@1.0.0/img/icon/JS.png
        color: '#f7cb4f'
      Kotlin:
        img: https://npm.elemecdn.com/wleelw-blog-abs@1.0.0/img/icon/kotlin-logo.svg
        color: '#ffffff'
      Docker:
        img: https://npm.elemecdn.com/wleelw-blog-abs@1.0.0/img/icon/docker.png
        color: '#57b6e6'
      Flutter:
        img: https://npm.elemecdn.com/wleelw-blog-abs@1.0.0/img/icon/flutter.png
        color: '#ffffff'
      WebPack:
        img: https://npm.elemecdn.com/wleelw-blog-abs@1.0.0/img/icon/webpack.png
        color: '#2e3a41'
      Git:
        img: https://npm.elemecdn.com/wleelw-blog-abs@1.0.0/img/icon/git.png
        color: '#df5b40'
      VS:
        img: https://npm.elemecdn.com/wleelw-blog-abs@1.0.0/img/icon/vs-logo.svg
        color: '#ffffff'

  # 顶部三大分类
  # Top three categories
  categoryGroup:
    # 左侧
    # Left
    G1:
      # 显示文字
      # Displayed text
      name: 必看精选
      # 显示图标
      # Displayed icon
      icon: scoicon sco-star-smile-fill
      # 跳转链接
      # Jump link
      url: /tags/精选/
    # 中间
    # Middle
    G2:
      name: 热门文章
      icon: scoicon sco-fire-fill
      url: /categories/热门/
    # 右侧
    # Right
    G3:
      name: 实用教程
      icon: scoicon sco-book-mark-fill
      url: /tags/教程/

  # 右侧置顶列表（在文章的front matter中添加“recommend: true”）
  # Right top list (add "recommend: true" in the front matter of the article)
  recommendList:
    # 左上角显示文字
    # Large text displayed in the upper left corner
    sup: 置顶
    # 左下角大字
    # Large text in the lower left corner
    title: Solitude主题文档
    # 点击跳转链接
    # Click the jump link
    url: https://docs.wzsco.top/
    # 显示背景图片
    # Display background image
    img: /img/default.png
    # 阴影颜色
    # Shadow color
    color: 'none'
```

{% note info %}
开启 banner 必须填写 icon ，否则会报错。 开启后可在文章的front matter中添加recommend: true，即可在右侧显示置顶文章。
{% endnote %}

## 侧边栏

**主题配置文件**: `_config.solitude.yml`

```yaml
home: # 在主页显示的侧边栏信息
  noSticky: "about"
  Sticky: "allInfo"
post: # 在文章页显示的侧边栏信息
  noSticky: "about"
  Sticky: "newestPost"
page: # 在页面中显示的侧边栏信息
  noSticky: "about"
  Sticky: "newestPost,allInfo"
```

> Sticky: 跟随，noSticky: 不跟随 Sticky和noSticky的值：about、allInfo、newestPost、flip

### 个人信息卡片

**主题配置文件**: `_config.solitude.yml`

```yaml
# 侧边栏个人信息卡片
# Sidebar personal information
card:
  # 头像信息
  # Avatar information
  author:
    # 头像
    # Avatar
    img: https://bu.dusays.com/2023/11/08/654af68b25bb8.jpg
    # 表情图片链接
    # Emoticon image link
    # tip: 推荐尺寸 26x26
    # tip: Recommended size 26x26
    sticker: https://bu.dusays.com/2023/12/30/659011053e246.png
  # 文案1
  # label1
  # tip：可使用html标签
  # tip: html tags can be used
  content: 分享自己对编程的<b>热爱</b>，对美好生活的<b>向往</b>，对知识海洋<b>探索历程</b>。
  # 文案2
  # label2
  # tip：可使用html标签
  # tip: html tags can be used
  content2: 相信你可以在这里找到对你有用的知识和教程。
  # 个人信息卡片底部的小图标，按照例子填写
  # Small icons at the bottom of the personal information card, fill in according to the example
  # 个人信息卡片顶部按钮的打招呼语句
  # Greeting statement of the button at the top of the personal information card
  sayhello:
    morning: 一日之计在于晨
    noon: 吃饱了才有力气干活
    afternoon: 集中精力，攻克难关
    night: 不要太劳累了，早睡更健康
    goodnight: 睡个好觉，保证精力充沛
  # 个人信息卡片顶部按钮的切换文字
  # Switching text of the button at the top of the personal information card
  sayhello2:
    - 🤖️ 数码科技爱好者
    - 🔍 分享与热心帮助
    - 🏠 智能家居小能手
    - 🔨 设计开发一条龙
    - 🤝 专修交互与设计
    - 🏃 脚踏实地行动派
    - 🧱 团队小组发动机
    - 💢 壮汉人狠话不多
    - 🎮 电竞游戏爱好者
  # 个人信息卡片底部的小图标，按照例子填写
  # Small icons at the bottom of the personal information card, fill in according to the example
  information:
    # 悬停显示文字
    Github:
      # 图标
      icon: scoicon sco-github-line
      # 跳转链接
      url: https://github.com/DuoSco/Hexo-Theme-slitude
    Bilibili:
      icon: scoicon sco-bilibili-line
      url: https://space.bilibili.com/1329819902
```

### 推荐二维码

**主题配置文件**: `_config.solitude.yml`

```yaml
# 二维码
# Official account QR code
flip:
  # 右下角头像
  # Avatar in the lower right corner
  favicon:
  # 正面
  # Front
  face:
  # 鼠标悬停翻转图片
  # Mouse hover flip image
  backface:
  # 夜间模式下是否开启卡片背景颜色 true：使用背景颜色 / false：不使用背景颜色
  # Whether to enable card background color in night mode true: use background color / false: do not use background color
  darkcolor: false
```

### 目录

**主题配置文件**: `_config.solitude.yml`

```yaml
# 页面目录
# Page directory
toc:
  # 在文章页显示
  # Display on the article page
  post: true
  # 在任意页显示
  # Display on any page
  page: false
  # 开启后不悬停目录有模糊效果
  # After opening, there is a fuzzy effect without hovering over the directory
  vague: true
```

### 标签

**主题配置文件**: `_config.solitude.yml`

```yaml
# 侧边栏文章列表
# Sidebar article list
tags:
  enable: false
  # 显示标签数量，当高于标签总数时，显示全部标签按钮
  # Display the number of tags, when it is higher than the total number of tags, display all tags button
  limit: 20
  # 高亮显示
  # Highlight
  highlight: false
  # 高亮显示标签列表
  # Highlighted tag list
  list:
    - 'Solitude-使用'
```

### 归档

**主题配置文件**: `_config.solitude.yml`

```yaml
# 侧边栏归档
# aside archive
archive:
  enable: false
  # 显示类型
  type: 'month' # monthly: 按月 / yearly: 按年 : monthly: by month / yearly: by year
```

### 建站信息

**主题配置文件**: `_config.solitude.yml`

```yaml
# 建站信息
# Website information
siteinfo:
  # 文章数
  # Number of articles
  postcount: true
  # 总字数
  # Total number of words
  wordcount: true
  # 访问量
  # Number of visits
  pv: true
  # 访客数
  # Number of visitors
  uv: true
  # 最后更新日期
  # Last update date
  updatetime: true
  # 建站时间
  # Website creation time
  runtimeenable: true
  # 格式：yyyy-MM-dd hh-mm-ss
  # Format: yyyy-MM-dd hh-mm-ss
  runtime: '2023-04-20 00:00:00'
```

{% note info %}
那年今日、个性定位卡片已删除，请自行添加自定义卡片，保留教程在作者博客。
{% endnote %}

## 页面默认配置

**主题配置文件**: `_config.solitude.yml`

```yaml
# 页面默认设置
# page default settings
page:
  error: true  # 404页面 / 404 page
  tags: true # 标签页 /  Tags page
  categories: true # 分类页 /  Categories page
  default: # 默认值 /  Default value
    # 默认图片
    # default cover
    # tip：随机数组图片，每次生成的时候都会从中随机抽取一张
    # tip: Random array pictures, each time you generate, you will randomly extract one from them
    cover:
      - /img/default.png # 默认图片 / default cover
```

## 文章默认配置

**主题配置文件**: `_config.solitude.yml`

```yaml
# 文章页默认设置
# post default settings
post:
  default:
    # 文章默认图片
    # default cover
    cover:
      - /img/default.png # 默认图片 / default cover
    # 文章发布默认地址
    # default post locate
    locate: 衡阳
    # 文章默认版权
    # default post copyright
    copyright:
      enable: true
      license: CC BY-NC-SA 4.0
      licenurl: https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh
      # 是否使用移轴动画头像
      # Whether to use the shift animation avatar
      author:
        enable: false
        author_back: https://bu.dusays.com/2023/11/01/6541f6d4b2573.png # 底部头像背景 / Bottom avatar background
  # 顶部文章简介
  # Top article introduction
  meta:
    date: false # 发布日期 / Release date
    updated: false # 更新日期 / Update date
    locate: false # 位置 / Location
    wordcount: false # 字数 / Number of words
    readtime: false # 访问 / uv
    pv: false # 浏览量 / pv
    comment: false # 评论数 / Comment count
  # 打赏
  # reward
  award:
    enable: false
    # 微信收款码
    # WeChat payment code
    wechat: https://bu.dusays.com/2023/11/07/6549e79364fa3.png
    # 支付宝收款码
    # Alipay payment code
    alipay: https://bu.dusays.com/2023/11/07/6549e79d02bd6.png
    # 打赏统计页面链接
    # Reward statistics page link
    url: /about
  # 版权中订阅按钮跳转链接，填写地址后开启
  # Subscription button jump link in copyright
  rss: # /atom.xml
  # 文章主题色获取
  # Article theme color acquisition
  covercolor:
    enable: false
    mode: local # local：本地取色 / api：img2color取色 : local: local color / api: img2color color
    api: https://img2color.wzsco.top/api?img= # api地址 / api address
    time: 43200000 # api取色间隔（毫秒），默认为12小时 / api color interval (milliseconds), default is 12 hours
```

## 自定义主题

### 主色调

**主题配置文件**: `_config.solitude.yml`

```yaml
# 自定义配色
# custom theme color
# 注意：颜色值必须使用引号，如“#000”，否则可能会导致错误！
# Note: The color value must be enclosed in quotation marks, such as "#000", otherwise it may cause an error!
# --------------------------------------
theme_color:
  dark: "#ffc848" # 暗色模式 / Dark mode
  dark_op: '#f2b94b23' # 暗色模式透明 / Dark mode transparent
  dark_op_deep: '#f2b94bdd' # 暗色模式透明深色 / Dark mode transparent dark
  dark_none: '#f2b94b00' # 暗色模式透明无色 / Dark mode transparent colorless
  light: "#425AEF" # 亮色模式 / Light mode
  light_op: '#4259ef23' # 亮色模式透明 / Light mode transparent
  light_op_deep: '#4259efdd' # 亮色模式透明深色 / Light mode transparent dark
  light_none: '#4259ef01' # 亮色模式透明无色 / Light mode transparent colorless
```

### 显示模式

**主题配置文件**: `_config.solitude.yml`

```yaml
# 主题显示模式调整
# theme display mode adjustment
# 主题支持三种模式：自动切换、暗色模式、亮色模式
# The theme supports three modes: automatic switching, dark mode, and light mode
# --------------------------------------
display_mode:
  type: auto # auto: 自动切换 / dark: 暗色模式 / light: 亮色模式 / auto: automatic switching / dark: dark mode / light: light mode
  universe: true # 开启后暗色模式下会显示星空背景 / After opening, the dark mode will display the starry sky background
```

## 推荐文章

{% note info %}
开启后，文章底部会显示相同标签、分类的文章。
{% endnote %}

**主题配置文件**: `_config.solitude.yml`

```yaml
# 文章底部推荐文章
related_post:
  enable: true  # 是否开启推荐
  limit: 2 # 推荐文章数量
  date_type: created # 根据创建日期（created）或是更新日期（updated）
```