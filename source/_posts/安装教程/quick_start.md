---
title: Solitude 安装文档(一) 快速开始
categories:
  - Docs
tags:
  - Docs
abbrlink: a0e4c699
date: 2024-02-16 00:00:00
cover: https://bu.dusays.com/2024/02/16/65cf175219f61.png
---

## 作者的话

请注意_config.solitude.yml中的配置优先级大于主题的_config.yml ，所以更新主题后需要比对主题文件夹中的theme/solitude/_config.yml 文件内容，一般在[release](https://github.com/DuoSco/Hexo-theme-solitude/releases)的说明里会特别提示或给出配置文件版本对比diff，同步修改原配置文件即可。

本指南并未包含所有配置的说明，但几乎每个配置在主题配置中都有注释，你可以结合指南和注释一起参考使用。

此外，本指南仅包含主题范围内的使用说明。如果涉及到 Hexo 的使用或 Hexo 插件的使用，请参阅它们各自的文档。

若存在其他主题相关的疑问请在 [issues](https://github.com/DuoSco/Hexo-theme-solitude/issues) 留言。

## 安装

{% note success ,sco-lightbulb-fill %}
Solitude主题拥有Main(稳定)和Dev(测试)两种版本, 我们推荐你安装使用Github(稳定)以获得最佳的主题体验
{% endnote %}

{% tabs 安装 %}

<!-- tab Git安装(GitHub) @sco-github-fill -->

**稳定版【建议】**

在你的 Hexo 根目录里

```bash
git clone -b main https://github.com/wleelw/hexo-theme-solitude.git themes/solitude
```

**测试版**

测试版可能存在 bug，追求稳定的请安装稳定版

如果想要安装比较新的 dev 分支，可以

```bash
git clone -b dev https://github.com/wleelw/hexo-theme-solitude.git themes/solitude
```

{% note info %}
升级方法：在主题目录下，运行 `git pull`
{% endnote %}

<!-- endtab -->

<!-- tab Git安装(Gitee) -->

**稳定版【建议】**

在你的 Hexo 根目录里

```bash
git clone -b main https://gitee.com/nsjjd_w/hexo-theme-solitude.git themes/solitude
```

**测试版**

测试版可能存在 bug，追求稳定的请安装稳定版

如果想要安装比较新的 dev 分支，可以

```bash
git clone -b dev https://gitee.com/nsjjd_w/hexo-theme-solitude.git themes/solitude
```

{% note info %}
升级方法：在主题目录下，运行 `git pull`
{% endnote %}

<!-- endtab -->

<!-- tab NPM安装 @sco-npmjs-fill -->

>此方法只支持 Hexo 5.0.0 以上版本
>通过 npm 安装并不会在 themes 里生成主题文件夹，而是在 node_modules 里生成

在你的 Hexo 根目录里

```bash
npm install hexo-theme-solitude
```

{% note info %}
升级方法：在主题目录下，运行 `npm update hexo-theme-solitude`
{% endnote %}

<!-- endtab -->

{% endtabs %}

## 应用主题

修改Hexo根目录下的配置文件`_config.yml`，将`theme`字段的值改为`solitude`。

```yaml
theme: solitude
```

## 安装插件

Solitude主题需要以下插件的支持：

```bash
npm install hexo-renderer-pug hexo-renderer-stylus --save
```

## 语言配置

修改站点配置文件_config.yml，不是主题配置文件
主题支持语言: zh-CN (简体中文)、en-US (美式英文)、zh-TW (繁体中文)

```yaml
language: zh-CN
```

## 本地启动

```bash
hexo clean && hexo g && hexo s --debug
```

## 更好的配置

在博客根目录运行以下命令，将主题的配置文件复制到根目录，以便更好的配置主题，方便主题更新。

{% tabs 更好的配置 %}

<!-- tab Git安装(GitHub) @sco-github-fill -->

**macOS/Linux**

```bash
cp themes/solitude/_config.yml _config.solitude.yml
```

**Windows**

```bash
copy themes\solitude\_config.yml _config.solitude.yml
```

<!-- endtab -->

<!-- tab Git安装(Gitee) -->
**macOS/Linux**
```bash
cp themes/solitude/_config.yml _config.solitude.yml
```

**Windows**
```bash
copy themes\solitude\_config.yml _config.solitude.yml
```

<!-- endtab -->

<!-- tab NPM安装 @sco-npmjs-fill -->

**macOS/Linux**

```bash
cp node_modules/hexo-theme-solitude/_config.yml _config.solitude.yml
```

**Windows**

```bash
copy node_modules\hexo-theme-solitude\_config.yml _config.solitude.yml
```

<!-- endtab -->

{% endtabs %}

## 视频教程

如果无法通过文档成功配置，这里有视频 Solitude 主题使用教程，供参考。

{% bilibili //player.bilibili.com/player.html?aid=579311071&bvid=BV1z64y1j7gs&cid=1355438788&p=1 %}

## 版本号释义

本项目的版本号为 X.Y.Z 格式，但与常见的[语义化版本号规范](https://semver.org/lang/zh-CN/)有部分区别，具体释义如下：

* X: 产品层面的重新设计，包含重大框架重构，会涉及大范围功能变更与配置变更，更新前必须阅读相关文档
* Y: 包含中大型新功能，及无法向下兼容的功能变更与配置变更，更新该版本号可能会需要修改配置或者移除一些原功能
* Z: 不仅包含 BUG 修复、小型新功能，还会包含可以向下兼容的原功能更新与配置变更，原则上更新该版本号无需额外动作