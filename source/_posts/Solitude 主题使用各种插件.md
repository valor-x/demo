---
title: 推荐插件
recommend: true
tags:
  - [ Solitude ]
  - [ 精选 ]
categories:
  - [ 我的项目,Solitude ]
abbrlink: 78307c7c
cover: https://bu.dusays.com/2024/01/24/65b112284a38e.png
date: 2023-12-28 21:25:00
---

{% note info flat %}
展示 Solitude 主题第三方插件的使用方式，不保证所有插件都能正常使用，有问题请评论区留言。
{% endnote %}

## abbrlink (短链接)

{% note info flat %}
百度蜘蛛抓取网页的规则:
对于蜘蛛说网页权重越高、信用度越高抓取越频繁，例如网站的首页和内页。蜘蛛先抓取网站的首页，因为首页权重更高，并且大部分的链接都是指向首页。然后通过首页抓取网站的内页，并不是所有内页蜘蛛都会去抓取。
搜索引擎认为对于一般的中小型站点，3层足够承受所有的内容了，所以蜘蛛经常抓取的内容是前三层，而超过三层的内容蜘蛛认为那些内容并不重要，所以不经常爬取。出于这个原因所以permalink后面跟着的最好不要超过2个斜杠。
{% endnote %}

1. 安装插件
    ```bash
    npm install hexo-abbrlink --save
    ```
2. 修改根目录配置文件`_config.yml`
    ```yaml
    ## permalink 修改原有
    permalink: posts/:abbrlink.html  # :/abbrlink
    ## abbrlink 新增
    abbrlink:
      alg: crc32 #支持 crc16(默认) and crc32
      rep: hex #支持 dec(默认) and hex
      drafts: false   #(true)Process draft,(false)Do not process draft. false(default) 
      # Generate categories from directory-tree
      # depth: the max_depth of directory-tree you want to generate, should > 0
      auto_category:
        enable: true  #true(default)
        depth:        #3(default)
        over_write: false
      auto_title: false #enable auto title, it can auto fill the title by path
      auto_date: false #enable auto date, it can auto fill the date by time today
      force: false #enable force mode,in this mode, the plugin will ignore the cache, and calc the abbrlink for every post even it already had abbrlink. This only updates abbrlink rather than other front variables.
    ```
3. 运行
    ```bash
    hexo clean && hexo g && hexo server
    ```
   {% note warning flat %}
   注意：如果有的文章已经生成了`abbrlink`，需要把文章的`front-matter`中删掉`abbrlink`字段，然后重新生成。
   {% endnote %}

## nofollow (外链添加 nofollow)

{% note info flat %}

为网站使用到的所有外链添加rel="noopener external nofollow noreferrer", 可以有效地加强网站 SEO 和防止权重流失。
更多关于 nofollow 的介绍可以参考 [nofollow - SEO百科](https://baike.baidu.com/item/Nofollow/2410595?fr=ge_ala)

{% endnote %}

1. 安装插件
    ```bash
    npm install hexo-filter-nofollow --save
    ```
2. 修改根目录配置文件`_config.yml`
    ```yaml
    # hexo-filter-nofollow
    nofollow:
      enable: true
      field: site
      exclude: # 去除不需要添加的
        - 'exclude1.com'
        - 'exclude2.com'
   ```
3. 运行
    ```bash
    hexo clean && hexo g && hexo server
    ```

## sitemap (站点地图)

{% note info flat %}

生成站点地图，方便搜索引擎抓取。

{% endnote %}

1. 安装插件
    ```bash
    npm install hexo-generator-sitemap --save
    ```
2. 修改根目录配置文件`_config.yml`
    ```yaml
   # sitemap hexo-generator-sitemap
   sitemap:
    path:
      - sitemap.xml
      - sitemap.txt
    template:
    template_txt:
    rel: false
    tags: true
    categories: true
   ```
3. 运行
    ```bash
    hexo clean && hexo g && hexo server
    ```
4. 验证
    查看站点根目录下是否生成了`sitemap.xml`文件，如果有则说明生成成功。