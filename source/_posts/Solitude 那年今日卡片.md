---
title: 那年今日卡片
recommend: true
tags:
  - [Solitude]
  - [ 精选]
categories:
  - [我的项目,Solitude]
cover: 'https://bu.dusays.com/2024/01/24/65b115f761178.png'
abbrlink: 22bd8b7c
date: 2024-01-08 00:00:00
---

> 本教程适用于 Solitude 主题 v1.3.1 以后版本，其他主题请自行测试。

## 介绍

那年今日卡片，效果如下：

![那年今日卡片](https://bu.dusays.com/2024/01/24/65b11d50d491a.png)

## 教程

1. 在 `source` 文件夹下找到 `_data` 文件夹（没有先新建），找到 `aside.yml` 文件（没有先新建）。在 `aside.yml` 文件中添加如下代码：
    ```yml
    home: # 如果在首页显示
      noSticky: # 如果需要固定在右侧
        - class_name: card-history
          id_name:
          name: 那年今日
          icon: scoicon sco-clock-fill
          class_content:
          id_content: history-baidu
          style_content: 'height:100px;overflow:hidden'
          html: '<div class="history_swiper-container" id="history-container" style="width: 100%;height: 100%;margin-top: 6px">
            <div id="history_container_wrapper" class="swiper-wrapper"></div>
          </div>'
    ```
2. 在 `source` 文件夹下找到 `css` 文件夹（没有先新建），找到 `custom.css` 文件（没有先新建）。在 `custom.css` 文件中添加如下代码：
    ```css
    /**
    那年今日
    */
    
    #aside-content .card-history .swiper-wrapper {
        flex-direction: column
    }
    
    #aside-content .card-history .history_slide {
        text-align: left;
        display: flex!important;
        flex-direction: column;
        align-items: flex-start
    }
    
    #aside-content .card-history #history-baidu>.blog-slider__pagination {
        display: none
    }
    
    #aside-content .card-history .history_slide_time {
        color: var(--sco-secondtext);
        font-size: 14px;
        font-style: italic;
        font-weight: lighter
    }
    
    #aside-content .card-history .history_slide_link {
        line-height: 1.5;
        -webkit-line-clamp: 2;
        display: -webkit-box;
        overflow: hidden;
        -webkit-box-orient: vertical
    }
    
    #aside-content .card-history .history_slide_link a {
        color: var(--sco-main);
        padding: 0 4px;
        border-radius: 4px
    }
    
    #aside-content .card-history .history_slide_link a:hover {
        color: var(--sco-white);
        background: var(--sco-main)
    }
   ```
3. 在 `source` 文件夹下找到 `js` 文件夹（没有先新建），找到 `custom.js` 文件（没有先新建）。在 `custom.js` 文件中添加如下代码：
    ```js
    // 那年今日
    (function() {
        async function fetchHistoryData() {
            const myDate = new Date();
            const myMonth = myDate.getMonth() + 1;
            const getDate = myDate.getDate();
            const getMonth = myMonth < 10 ? "0" + myMonth : "" + myMonth;
            const getDay = getDate < 10 ? "0" + getDate : "" + getDate;
            const getMonthDate = "S" + getMonth + getDay;
            const history_data_url = `https://fastly.jsdelivr.net/gh/Zfour/Butterfly-card-history@2.08/baiduhistory/json/${getMonth}.json`;

            const response = await fetch(history_data_url);
            const data = await response.json();
            return data[getMonthDate];
        }

        function append(parent, text) {
            const temp = document.createElement('div');
            temp.innerHTML = text;
            const frag = document.createDocumentFragment();
            while (temp.firstChild) {
                frag.appendChild(temp.firstChild);
            }
            parent.appendChild(frag);
        }

        function card_history() {
            if (document.getElementById('history-container')) {
                fetchHistoryData().then(data => {
                    const html_item = data.map(item => `
            <div class="swiper-slide history_slide">
                <span class="history_slide_time">A.D.${item.year}</span>
                <span class="history_slide_link">${item.title}</span>
            </div>
            `).join('');
                    const history_container_wrapper = document.getElementById('history_container_wrapper');
                    append(history_container_wrapper, html_item);
                    const swiper_history = new Swiper('.history_swiper-container', {
                        passiveListeners: true,
                        spaceBetween: 30,
                        effect: 'coverflow',
                        coverflowEffect: {
                            rotate: 30,
                            slideShadows: false,
                        },
                        loop: true,
                        direction: 'vertical',
                        autoplay: {
                            disableOnInteraction: true,
                            delay: 5000
                        },
                        mousewheel: false,
                    });
                    const history_container = document.getElementById('history-container');
                    history_container.onmouseenter = function () {
                        swiper_history.autoplay.stop();
                    };
                    history_container.onmouseleave = function () {
                        swiper_history.autoplay.start();
                    }
                });
            }
        }

        card_history();

        document.addEventListener('pjax:complete', card_history);
    })();
    ```
4. 在主题配置文件`_config.solitude.yml`的 `extends` 的 `head` 中添加如下：
   ```yml
   - <link rel="stylesheet" href="/css/custom.css">
   ```
5. 在主题配置文件`_config.solitude.yml`的 `extends` 的 `body` 中添加如下：
   ```yml
   - <script src="/js/custom.js"></script>
   ```
   
{% note warning no-icon modern %}
如果你没有使用 即刻短文的话，还需要在 `extends` 的 `body` 中添加如下：
```yml
- <link rel="stylesheet" href="https://lf9-cdn-tos.bytecdntp.com/cdn/expire-1-M/Swiper/8.0.6/swiper-bundle.min.css">
- <script src="https://lf9-cdn-tos.bytecdntp.com/cdn/expire-1-M/Swiper/8.0.6/swiper-bundle.min.js"></script>
```
可自行更换CDN。
{% endnote %}