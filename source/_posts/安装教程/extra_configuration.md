---
title: Solitude 安装文档(四) 额外配置
categories:
  - Docs
tags:
  - Docs
abbrlink: 29d77ad0
date: 2024-02-16 03:00:00
cover: https://bu.dusays.com/2024/02/16/65cf1b89c382a.png
---

## 页脚 （Footer）

### 上方图标

**主题配置文件**: `_config.solitude.yml`

```yaml
  # 底部上方一排图标
  # Bottom row of icons
  information:
     left: # 左侧显示图标
       Github: https://github.com/wleelw || sco-github-line # 名称：链接 || 图标 / Name: link || icon
       Mail: mailto:wleelw@wzsco.top || sco-mail-line
     right: # 右侧显示图标
       Bilibili: https://space.bilibili.com/1329819902 || sco-bilibili-line
       抖音: https://v.douyin.com/iJsLc8jt/ || sco-douyin-fill
```

![information](https://bu.dusays.com/2024/03/01/65e1a31e36b10.png)

### 导航栏

**主题配置文件**: `_config.solitude.yml`

```yaml
  # 底部导航栏
  # Bottom navigation bar
  group:
    导航:
      归档: /archives/
      分类: /categories/
      标签: /tags/
    服务:
      阿里云: https://aliyun.com/
      51la统计: https://v6.51.la/
      百度统计: https://tongji.baidu.com/
    支持:
      打赏记录: /about/
    协议:
      Cookies: /cookies/ 
      用户协议: /privacy/ 
      版权协议: /copyright/
```

![底部导航栏](https://bu.dusays.com/2024/03/01/65e1a3e06e5fd.png)

### 页脚信息

**主题配置文件**: `_config.solitude.yml`

```yaml
  # 底部随机友链
  # Random links at the bottom
  # tip：此处的友链是随机显示的，不是固定的
  # tip: The links here are displayed randomly, not fixed
  # warning: 打开前必须先配置links
  # warning: links must be configured before opening
  randomlink: false
  # 隐私助手右侧弹窗，填写路径后开启
  # Privacy assistant right pop-up window, fill in the path to open
  privacy: # /privacy/
  # 版权
  # Copyright
  license: # /license/
  # 页脚右侧链接，例如：ICP备案号、公安备案号等
  # Footer right link, such as: ICP filing number, public security filing number, etc.
  links:
     # 为了主题能够得到更多的支持，建议保留主题链接
     # In order for the theme to get more support, it is recommended to keep the theme link
     - name: 主题
       url: https://github.com/wleelw/hexo-theme-solitude
  #    - name: 订阅
  #      url: /atom.xml
```

![页脚信息](https://bu.dusays.com/2024/03/01/65e1a42de12e2.png)

## 404 页面

> 自定义 404 页面内容

**主题配置文件**: `_config.solitude.yml`

```yaml
# 404 页面
# 404 page
errorpage:
  # 图片
  # image
  img: https://bu.dusays.com/2023/03/03/6401a7906aa4a.gif
  # 文字
  # text
  text: =awa= 页面走丢了
  # 推荐文章列表
  # Recommended article list
  recommendList: true
```

## 音乐胶囊

**主题配置文件**: `_config.solitude.yml`

```yaml
# 音乐胶囊
# capsule music
capsule:
  enable: false
  id: 8407304077 # 歌单id / playlist id
  server: netease # 播放列表的服务商。netease：网易云 / tencent：腾讯 / kugou：酷狗 / xiami：小米 / baidu：百度 : Music service provider. netease: Netease Cloud / tencent: Tencent / kugou: Kugou / xiaomi: Xiaomi / baidu: Baidu
  type: playlist # 播放列表的类型。song：单曲 / playlist：歌单 / album：专辑 / artist：歌手 : Type of playlist. song: Single / playlist: Playlist / album: Album / artist: Singer
```

![音乐胶囊](https://bu.dusays.com/2024/03/01/65e1a4d523477.png)

## 快捷菜单

> 配置可参考作者文章：[Solitude主题使用：如何配置快捷菜单](https://blog.wzsco.cn/p/88973ede.html)

**主题配置文件**: `_config.solitude.yml`

```yaml
keyboard:
  enable: false # 是否开启键盘控制 / Whether to enable keyboard control
  # 键盘控制配置
  # Keyboard control configuration
  list:
  # name: 按键名称
  # name: Key name
  # key: 按键
  # key: Key
  # func: 方法
  # func: Function
  # sco: sco内置方法
  # sco: sco built-in method
  # url: 跳转链接
  # url: Jump link
#    - name: 关闭快捷键功能
#      key: K
#      func: keyboard
#    - name: 打开中控台
#      key: A
#      sco: showConsole
#    - name: 播放/暂停音乐
#      key: M
#      sco: musicToggle
#    - name: 打开友情链接
#      key: L
#      url: '/links/'
```

![快捷菜单](https://bu.dusays.com/2024/03/01/65e1a5055f42d.png)

## 懒加载

> 懒加载是一种网页性能优化技术，它可以延迟加载页面上的图片、视频、音频等资源，当用户滚动到它们的位置时再加载。

**主题配置文件**: `_config.solitude.yml`

```yaml
# 懒加载
# lazyload
lazyload:
  enable: false
  # 加载中显示图片
  # Loading display image
  placeholder: /img/loading.gif
  # 加载失败显示图片
  # Loading failed display image
  errorimg: /img/error_load.png
```

## 加载动画

> 加载动画是一种网页性能优化技术，它可以等待页面上的图片、视频、音频等资源加载完之后显示。

**主题配置文件**: `_config.solitude.yml`

```yaml
# 加载动画
# loading animation
loading:
  # 全局加载动画
  # Global loading animation
  fullpage: false
  # 顶部加载胶囊
  # Top loading capsule
  pace: true
```

## 代码高亮

> 代码高亮是一种网页性能优化技术，它可以让代码更加美观。

**主题配置文件**: `_config.solitude.yml`

```yaml
#代码高亮增强
# code highlight
hightlight:
  enable: false
  # 代码块行高限制
  # Code block line height limit
  hightlimit: 200
  copy: true # 是否开启复制按钮 / Whether to enable the copy button
  expand: false # 是否默认展开 / Whether to expand by default
  # 代码块样式
  # Code block style
  theme: default # default: 默认 / mac : apple terminal
  # 代码配色
  # Code color
  color: default # default: 默认  / vscode / solarized-dark / solarized-light / dracula / monokai
```

## 图片灯箱

> fancybox 和 mediumZoom 二选一
> 一定要关闭 fancybox 才能开启 mediumZoom

**主题配置文件**: `_config.solitude.yml`

```yaml
# image lightbox
lightbox: true # 是否开启图片灯箱

# fancybox
# https://fancyapps.com/fancybox/
fancybox: true

# mediumZoom
mediumZoom: false
```

## 简繁转换

> 此功能需要开启主题右键菜单才能使用 开启后，网站右键菜单会有简繁转换选项

**主题配置文件**: `_config.solitude.yml`

```yaml
# 简繁转换
# Simplified and Traditional Chinese conversion
translate:
  enable: false
  # the language of website (1 - Traditional Chinese/ 2 - Simplified Chinese）
  defaultEncoding: 2
  # Time delay
  translateDelay: 0
```

## Open Graph

> Open Graph 是一种协议，它可以让网页在社交平台上更好的展示。

**主题配置文件**: `_config.solitude.yml`

```yaml
# Open Graph
# https://ogp.me/
# https://developers.facebook.com/docs/sharing/webmasters/
opengraph:
  enable: false
  options:
#    twitter_card:
#    twitter_image:
#    twitter_id:
#    twitter_site:
#    google_plus:
#    fb_admins:
#    fb_app_id:
```

## 字数统计

> 打开前需要安装 [hexo-wordcount](https://github.com/willin/hexo-wordcount)。

**主题配置文件**: `_config.solitude.yml`

```yaml
# 字数统计
# word count
# warning：开启前需要安装字数统计插件
# warning: You need to install the word count plugin before turning it on
wordcount: false
```

## 不蒜子

> 不蒜子是一款不蒜子统计网站访问量的插件。

**主题配置文件**: `_config.solitude.yml`

```yaml
# 访问统计
# access statistics
busuanzi: false
```

## 搜索

**主题配置文件**: `_config.solitude.yml`

```yaml
# 搜索
# search
# warning：开启前需要安装搜索插件
# warning: You need to install the search plugin before turning it on
search:
  enable: false
  # algolia, local
  type: algolia
  # 推荐标签
  # Recommended tags
  tags:
  #  - Solitude
  #  - Hexo
  algolia:
  # hits:
  #   per_page: 6
  local:
    preload: false
    CDN:
```

{% tabs 搜索 %}

<!-- tab Algolia搜索 -->

> 如果你使用 hexo-algoliasearch，请记得配置 fields 参数的 title, permalink 和 content

1. 安装 [hexo-algolia](https://github.com/oncletom/hexo-algolia) 或 [hexo-algoliasearch](https://github.com/LouisBarranqueiro/hexo-algoliasearch). 根据它们的使用文档去做相应的配置。
2. 在主题配置文件中开启搜索，并设置 type 为 algolia。

```yaml
# 搜索
# search
# warning：开启前需要安装搜索插件
# warning: You need to install the search plugin before turning it on
search:
  enable: true
  # algolia, local
  type: algolia
  # 推荐标签
  # Recommended tags
  tags:
  #  - Solitude
  #  - Hexo
  algolia:
  # hits:
  #   per_page: 6
  local:
    preload: false
    CDN:
```

<!-- endtab -->

<!-- tab 本地搜索 -->

1. 安装 [hexo-generator-searchdb](https://github.com/next-theme/hexo-generator-searchdb) 或者 [hexo-generator-search](https://github.com/PaicHyperionDev/hexo-generator-search)，根据它的文档去做相应配置
2. 在主题配置文件中开启搜索，并设置 type 为 local。

```yaml
# 搜索
# search
# warning：开启前需要安装搜索插件
# warning: You need to install the search plugin before turning it on
search:
  enable: true
  # algolia, local
  type: local
  # 推荐标签
  # Recommended tags
  tags:
  #  - Solitude
  #  - Hexo
  algolia:
  # hits:
  #   per_page: 6
  local:
    preload: false
    CDN:
```

<!-- endtab -->

<!-- tab 搜索标签 -->

> 你可以在这里设置推荐标签，这些标签将会在搜索页面显示。

```yaml
tags:
  - Solitude
  - Hexo
```

<!-- endtab -->

{% endtabs %}

## 右键菜单

> 技术原因，暂时需要先配置评论系统才能开启右键菜单

**主题配置文件**: `_config.solitude.yml`

```yaml
# rightside(右键菜单)
rightside:
  enable: false
```

## 文章摘要 AI

{% note info %}
使用前，tianliGPT的key请到[爱发电](https://afdian.net/item/f18c2e08db4411eda2f25254001e7c00) 中购买，10元5万字符（常有优惠）。请求过的内容再次请求不会消耗key，可以无限期使用。
购买完成后，进入[管理后台](https://docs.wzsco.top/zh/guide/summary.zhheo.com)：summary.zhheo.com ，登录后点击右上角的“添加新网站”，输入密钥即可绑定成功。
若需要进行本地调试，请在管理后台将 127.0.0.1 :端口 加入白名单，否则会触发防盗KEY，无法正常获取摘要。
{% endnote %}

**主题配置文件**: `_config.solitude.yml`

```yaml
# 文章摘要AI
# post abstract AI
post_ai:
  enable: false
  # 右侧显示的模型名称
  # Model name displayed on the right
  modelName: GPT 4
  # key
  # 具体获取方法见文档
  # Specific acquisition method, see the document
  key:
  # 自介
  # talk
  talk: 我是王卓Sco开发的摘要生成助理ScoGPT，ScoGPT在静态部署时进行摘要的撰写，并且在访客访问时通过ScoCorrection转译后的文本摘要实现工具。我在这里只负责已经生成的摘要显示，你无法与我直接沟通，但我可以回答一些预设的问题。
  # 随机文章按钮
  # Random post button
  randomPost: false
  # 举报链接，不填不显示
  # Report link, do not fill in and do not display
  report: https://blog.wzsco.top/about/
  # 底部提示
  # Bottom tip
  tips: 此内容根据文章生成，并经过人工审核，仅用于文章内容的解释与总结
```

## 数学公式

> 主题支持使用Katex数学公式 详细配置参考作者文章：[Solitude主题使用：如何配置Katex数学公式](https://blog.wzsco.top/p/b1d1f75b.html)

1. 更换markdown-it渲染器
    ```bash
    npm un hexo-renderer-marked --save # 卸载hexo-marked
    npm un hexo-renderer-kramed --save # 卸载hexo-kramed
    npm i hexo-renderer-markdown-it --save # 安装hexo-markdown-it
    npm install katex @renbaoshuo/markdown-it-katex # 安装katex扩展
    ```
2. 根目录配置文件_config.yml中添加如下配置：
    ```yaml
    # markdown-it
    markdown:
       preset: 'default'
       render:
          html: true
          xhtmlOut: false
          langPrefix: 'language-'
          breaks: true
          linkify: true
          typographer: true
          quotes: '“”‘’'
       enable_rules:
       disable_rules:
       plugins:
          - '@renbaoshuo/markdown-it-katex'
       anchors:
          level: 2
          collisionSuffix: ''
          permalink: true
          permalinkClass: 'headerlink'
          permalinkSide: 'left'
          permalinkSymbol: ''
          case: 0
          separator: '-'
       images:
          lazyload: true
          prepend_root: false
          post_asset: false
       inline: false
    ```
3. 在主题配置文件_config.solitude.yml中添加如下配置：
    ```yaml
    # latex 公式支持
    # latex formula support
    katex:
      enable: true
      per_page: false # 是否在每页都加载 / Whether to load on each page
      copytex: false # 是否开启复制公式 / Whether to enable copy formula
    ```
4. 在Solitude主题下，使用Katex非常简单，只需要在文章的头部添加`katex: true`即可，如下所示：（Page中也能使用Katex）
    ```markdown
    ---
    katex: true
    ---
    ```

## 评论

> 目前支持 twikoo 和 waline

**主题配置文件**: `_config.solitude.yml`

```yaml
# 评论
# comment
comment:
  enable: false
  type: # waline, twikoo
  commentBarrage: false # 热评开关 / Hot comment switch
  newComment: false # 最新评论开关 / Latest comment switch
  # 匿名评论前部分随机信息 / Anonymous comment front random information
  randomInfoStart:
    - '聪敏的'
    - '可爱的'
    - '美丽的'
  # 匿名评论后部分随机信息 / Anonymous comment after random information
  randomInfoEnd:
    - '白菜'
    - '小可爱'
    - '小仙女'
  # twikoo 配置信息
  # twikoo settings
  twikoo: # https://twikoo.js.org/
    envId: # url: https://twikoo.sondy.top/
    lang: 'zh-CN' # 语言
    accessToken:  # accessToken
  # waline 配置信息
  # waline settings
  waline: # https://waline.js.org/
    envId:  # url: https://waline.wzsco.top
    pageview: true # 是否开启页面访问量统计 / Whether to enable page access statistics
    option: # waline配置项 / waline configuration item
```

## 站点验证

**主题配置文件**: `_config.solitude.yml`

```yaml
# 站点验证
# Site verification
# 仅需要填写验证代码即可，譬如：codeva-KReTIJu5us
# Only need to fill in the verification code, such as: codeva-KReTIJu5us
verify_site:
#  - name: google-site-verification
#    content: xxxxxx
#  - name: baidu-site-verification
#    content: xxxxxxx
```

## CSS 前缀

**主题配置文件**: `_config.solitude.yml`

```yaml
# CSS 前缀
# CSS prefix
# 有些 CSS 并不是所有浏览器都支持，需要增加对应的前缀才会生效
# Some CSS is not supported by all browsers, and you need to add the corresponding prefix to take effect
# 开启 css_prefix 后，会自动为一些 CSS 增加前缀。（会增加 20%的体积）
# After opening css_prefix, some CSS will be automatically prefixed. (Will increase 20% of the volume)
css_prefix: false
```

## Inject

**主题配置文件**: `_config.solitude.yml`

```yaml
# 插入代码到头部 </head> 之前 和 底部 </body> 之前
# Insert code before </head> and before </body>
# 插入额外代码 如：统计，广告等
# Insert additional code such as: statistics, advertising, etc.
extends:
  head: # 在head中插入 / Insert in head
  #    - <script src="https://cdn.bootcdn.net/ajax/libs/pace/1.2.4/pace.min.js"></script>
  body: # 在body中插入 / Insert in body
```

## PWA

> PWA支持的前提条件：全站资源必须为HTTPS。

PWA 全称为 Progressive Web App，中文译为渐进式Web APP，其目的是通过各种 Web 技术实现与原生 App 相近的用户体验。 纵观现有 Web 应用与原生应用的对比差距，如离线缓存、沉浸式体验等等，可以通过已经实现的 Web 技术去弥补这些差距，最终达到与原生应用相近的用户体验效果。

1. 在 主题配置文件 中开启 pwa 选项
    ```yaml
    # PWA
    pwa:
      enable: true # 是否开启
      manifest: /manifest.json # manifest.json 文件路径
      theme_color: '#ffffff' # 主题颜色
      mask_icon: https://fastly.jsdelivr.net/npm/solitude-source@1.0.0/img/pwa/180.png # 遮罩图标
      apple_touch_icon: https://fastly.jsdelivr.net/npm/solitude-source@1.0.0/img/pwa/180.png # 苹果触摸图标
      bookmark_icon: https://fastly.jsdelivr.net/npm/solitude-source@1.0.0/img/pwa/180.png # 书签图标
      favicon_32_32: https://fastly.jsdelivr.net/npm/solitude-source@1.0.0/img/pwa/32.png # 32x32图标
      favicon_16_16: https://fastly.jsdelivr.net/npm/solitude-source@1.0.0/img/pwa/16.png # 16x16图标 
    ```
2. 安装 hexo-swpp、hexo-backends 插件
    ```yaml
    npm install hexo-swpp hexo-backends --save 
    ```
3. 修改 hexo 配置文件，新增以下内容
    ```yaml
     swpp:
       # 是否启用插件
       enable: true
       # 是否在发布前自动执行脚本
       # auto_exec: true
       # 构建时拉取版本文件的警告等级，缺省为 1（该功能仅在 swpp-backends 版本号 >= 2.1.2 时可用）
       # 0 - 表示不允许出现 404 情况；1 - 表示允许服务器返回 404 状态码；2 - 表示允许任何 404（包括 DNS 解析失败等）
       # warn_level: 1
       # 检查版本的 URL，不能以 '/' 结尾
       # npm_url: 'https://registry.npmmirror.com' 
    ```
4. 新建 [根目录]/source/manifest.json 文件，并新增以下内容 （里面的src图片地址可能无效，请更换自己的图片）
    ```json
      {
      "name": "Solitude",
      "short_name": "Solitude",
      "theme_color": "#ffffff",
      "background_color": "#ffffff",
      "display": "fullscreen",
      "scope": "/",
      "start_url": "/",
      "id": "/",
      "icons": [
        {
          "src": "/img/pwa/192.png",
          "sizes": "192x192",
          "type": "image/png",
          "purpose": "any"
        },
        {
          "src": "/img/pwa/192.png",
          "sizes": "192x192",
          "type": "image/png",
          "purpose": "maskable"
        },
        {
          "src": "/img/pwa/512.png",
          "sizes": "512x512",
          "type": "image/png",
          "purpose": "any"
        },
        {
          "src": "/img/pwa/512.png",
          "sizes": "512x512",
          "type": "image/png",
          "purpose": "maskable"
        }
      ],
      "splash_pages": null
    }
    ```
5. 新建 [根目录]/sw-rules.js 文件，并新增以下内容
    ```js
    module.exports.config = {
      /** @type {?ServiceWorkerConfig|boolean} */
      serviceWorker: {
        escape: 0,
        cacheName: 'SolitudeCache',
        debug: false
      },
      register: {
        onsuccess: undefined,
        onerror: () => console.error('Service Worker 注册失败！可能是由于您的浏览器不支持该功能！'),
        builder: (root, framework, pluginConfig) => {
          const {onerror, onsuccess} = pluginConfig.register;
          return `
             <script>
                 (() => {
                     const sw = navigator.serviceWorker;
                     const error = ${onerror && onerror.toString()};
                     if (!sw?.register('${new URL(root).pathname}sw.js')
                         ${onsuccess ? `?.then(${onsuccess.toString()})` : ''}
                         ?.catch(error)
                     ) error()
                 })()
             </script>`;
        }
      },
      /** @type {?DomConfig|boolean} */
      dom: {
        /** @type {?VoidFunction} */
        onsuccess: () => {
          caches.match(location.href).then(res => {
            if (res)
              res.json().then(json => {
                utils && utils.snackbarShow(`已刷新缓存，更新为${json.global + '.' + json.local}版本最新内容`, false, 2000)
              })
            else
              console.info('未找到缓存')
          }).catch((error) => console.error("缓存匹配出错", error))
        }
      },
      /** @type {?VersionJsonConfig|boolean} */
      json: {
        /** @type {number} */
        maxHtml: 15,
        /** @type {number} */
        charLimit: 1024,
        /** @type {string[]} */
        merge: [],
        exclude: {
          /** @type {RegExp[]} */
          localhost: [],
          /** @type {RegExp[]} */
          other: []
        }
      },
      /** @type {?ExternalMonitorConfig|boolean} */
      external: {
        /** @type {number} */
        timeout: 5000,
        /** 拉取文件时地并发限制 */
        concurrencyLimit: 100,
        /** @type {({head: string, tail: string}|function(string):string[])[]} */
        js: [],
        /** @type {RegExp[]} */
        stable: [
          /^https:\/\/npm\.elemecdn\.com\/[^/@]+\@[^/@]+\/[^/]+\/[^/]+$/,
          /^https:\/\/cdn\.cbd\.int\/[^/@]+\@[^/@]+\/[^/]+\/[^/]+$/,
          /^https:\/\/cdn\.jsdelivr\.net\/npm\/[^/@]+\@[^/@]+\/[^/]+\/[^/]+$/,
        ],
        replacer: srcUrl => {
          if (srcUrl.startsWith('https://cdn.jsdelivr.net/npm/')) {
            const pathname = new URL(srcUrl).pathname;
            return [
              srcUrl,
              `https://cdn.cbd.int/${pathname}`,
              `https://npm.elemecdn.com/${pathname}`,
              `https://fastly.jsdelivr.net/npm/${pathname}`,
            ];
          } else {
            return srcUrl;
          }
        }
      }
    };
    
    module.exports.cacheRules = {
      simple: {
        clean: true,
        search: false,
        match: (url,$eject) => url.host === $eject.domain && ["/404.html"].includes(url.pathname)
      },
      cdn: {
        clean: true,
        match: url => [
          "cdn.cbd.int",
          "lf26-cdn-tos.bytecdntp.com",
          "lf6-cdn-tos.bytecdntp.com",
          "lf3-cdn-tos.bytecdntp.com",
          "lf9-cdn-tos.bytecdntp.com",
          "cdn.staticfile.org",
          "npm.elemecdn.com",
        ].includes(url.host) && url.pathname.match(/\.(js|css|woff2|woff|ttf|cur)$/),
    
      }
    };
    
    module.exports.getSpareUrls = srcUrl => {
      if (srcUrl.startsWith("https://npm.elemecdn.com")) {
        return {
          timeout: 3000,
          list: [srcUrl, `https://fastly.jsdelivr.net/${new URL(srcUrl).pathname}`],
        };
      }
    }
    
    module.exports.ejectValues = (hexo, rules) => {
      return {
        domain: {
          prefix: "const",
          value: new URL(hexo.config.url).host,
        },
      };
    };
    
    module.exports.skipRequest = request => request.url.startsWith("https://i0.hdslb.com") ||
      request.url.startsWith('https://meting.qjqq.cn') ||
      request.url.startsWith('https://api.i-meto.com');
    ```
6. 全部步骤操作完成后，你可以通过Chrome控制台的 Lighthouse 检查 PWA 配置是否生效以及配置是否正确。
7. 图片素材下载地址：[Solitude PWA 图片素材](https://cdn.cbd.int/solitude-source@1.0.5/sketch/PWA%20-%20ICONS%20&%20%E9%97%AA%E5%B1%8F%E7%B4%A0%E6%9D%90.sketch)

## CDN

> 此部分切勿轻易修改，以保证稳定。

**主题配置文件**: `_config.solitude.yml`

```yaml
# CDN
# Don't modify the following settings unless you know how they work
# 非必要请不要修改
CDN:
   # The CDN provider of internal scripts (主题内 js 的 cdn 配置)
   # option: local/jsdelivr/unpkg/cdnjs/custom
   # Dev version can only choose. ( dev版本只能为 local )
   internal: local
   # The CDN provider of third party scripts (第三方 js 的 cdn 配置)
   # option: jsdelivr/unpkg/cdnjs/custom
   third_party: custom

   # Add version number to url, true or false
   version: true

   # Custom format
   # For example: https://cdn.staticfile.org/${cdnjs_name}/${version}/${min_cdnjs_file}
   custom_format: https://cdn.staticfile.org/${cdnjs_name}/${version}/${min_cdnjs_file}

   option:
      scoicon_css: https://cdn.cbd.int/solitude-source/icon/scoicon.min.css
      waterfall: https://cdn.cbd.int/solitude-source/js/waterfall.min.js
      universe_js: https://cdn.cbd.int/solitude-source/js/universe.min.js
#    algolia_search:
#    instantsearch:
#    pjax:
#    twikoo:
#    waline_js:
#    waline_css:
#    sharejs:
#    sharejs_css:
#    katex:
#    katex_copytex:
#    lazyload:
#    aplayer_css:
#    aplayer_js:
#    meting_js:
#    pace_js:
#    lunr_js:
#    swiper_css:
#    swiper_js:
#    busuanzi_js:
#    snackbar_css:
#    snackbar_js:
```