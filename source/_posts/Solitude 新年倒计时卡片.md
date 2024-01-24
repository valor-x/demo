---
title: 新年倒计时卡片
recommend: true
tags:
  - [ Solitude ]
  - [ 精选 ]
categories:
  - [ 我的项目,Solitude ]
cover: https://bu.dusays.com/2024/01/24/65b115dd700f8.png
abbrlink: e365d454
date: 2024-01-01 17:11:00
---

{% note info flat %}
灵感来自 Leonus 的博客，感谢 Leonus 的分享。
{% endnote %}

{% link 博客新年倒计时卡片 Leonus https://blog.leonus.cn/2023/newYearCard.html %}

1. 新建 `aside.yml` 文件在 `_data` 目录下，添加如下内容：
    ```yaml
   home:
    noSticky:
       - class_name:
         id_name: newYear
         name:
         icon:
         html: '<div id="newYear-main">
            <p class="title"></p>
            <div class="newYear-time"></div>
            <p class="today" style="text-align: right;"></p>
            </div>'
    Sticky:
   ```
2. 新建 `custom.css` 文件在 `[root]/source/css` 目录下（如果没有css文件夹，请新建），添加如下内容：
   ```css
   /* 新年侧边栏 */
   #newYear {
    color: var(--sco-card-bg);
    padding: 0 !important;
   }
   
   #newYear p,
   #newYear h3 {
    font-weight: normal;
    color: inherit;
    margin: 0;
   }
   
   #newYear .item-headline {
    display: none;
   }
   
   #newYear-main {
    min-height: 160px;
    padding: 1rem;
    position: relative;
    border-radius: 12px;
    background-color: var(--sco-theme);
   }
   
   #newYear-main * {
    position: relative;
    line-height: 1.3;
   }
   
   #newYear-main .newYear-time {
    font-weight: bold;
    text-align: center;
   }
   
   #newYear-main .time,
   #newYear-main .happyNewYear {
    font-size: 2rem;
    text-shadow: 2px 2px 2px red;
    margin: 1rem 0;
    display: block;
   }
   
   #newYear-main .day {
    font-size: 5rem;
   }
   
   #newYear-main .day .unit {
    font-size: 1rem;
   }
   ```
3. 新建 `newYear.js` 文件在 `[root]/source/js` 目录下（如果没有js文件夹，请新建），添加以下内容：
   ```js
   let newYearTimer = null;
   var newYear = () => {
   clearTimeout(newYearTimer);
   if (!document.querySelector('#newYear')) return;
   // 新年时间戳 and 星期对象
   let newYear = new Date('2024-02-10 00:00:00').getTime() / 1000,
   week = { 0: '周日', 1: '周一', 2: '周二', 3: '周三', 4: '周四', 5: '周五', 6: '周六' }
   
       time();
   
       // 补零函数
       function nol(h) { return h > 9 ? h : '0' + h; };
   
       function time() {
           // 现在 时间对象
           let now = new Date();
   
           // 右下角 今天
           document.querySelector('#newYear .today').innerHTML = now.getFullYear() + '年' + (now.getMonth() + 1) + '月' + now.getDate() + '日 ' + week[now.getDay()]
   
           // 现在与新年相差秒数
           let second = newYear - Math.round(now.getTime() / 1000);
   
           // 小于0则表示已经过年
           if (second < 0) {
               document.querySelector('#newYear .title').innerHTML = '喜迎新年';
               document.querySelector('#newYear .newYear-time').innerHTML = '<span class="happyNewYear">新年快乐！</span>';
           } else {
               // 大于0则还未过年
               document.querySelector('#newYear .title').innerHTML = '距离2024年春节：'
   
               // 大于一天则直接渲染天数
               if (second > 86400) {
                   document.querySelector('#newYear .newYear-time').innerHTML = `<span class="day">${Math.ceil(second / 86400)}<span class="unit">天</span></span>`
               } else {
                   // 小于一天则使用时分秒计时。
                   let h = nol(parseInt(second / 3600));
                   second %= 3600;
                   let m = nol(parseInt(second / 60));
                   second %= 60;
                   let s = nol(second);
                   document.querySelector('#newYear .newYear-time').innerHTML = `<span class="time">${h}:${m}:${s}</span></span>`;
                   // 计时
                   newYearTimer = setTimeout(time, 1000);
               }
           }
       }
   }
   newYear();
   
   document.addEventListener('pjax:complete', newYear);
   ```
4. 在主题配置文件的 `extends` 的 `head` 中添加如下内容：
   ```yaml
   - <link rel="stylesheet" href="/css/custom.css">
   ```
5. 在主题配置文件的 `extends` 的 `body` 中添加如下内容：
   ```yaml
   - <script src="/js/newYear.js"></script>
   ```
6. 执行 `hexo clean && hexo g && hexo server`，查看效果。
   ![倒计时](https://bu.dusays.com/2024/01/24/65b11d220b110.png)
   ![过年](https://bu.dusays.com/2024/01/24/65b11d35969e5.png)

{% note info flat %}
样式待更新，欢迎评论发表意见。
{% endnote %}