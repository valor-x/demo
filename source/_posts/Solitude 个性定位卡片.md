---
title: 个性定位卡片
recommend: true
tags:
  - [ Solitude ]
  - [ 精选 ]
categories:
  - [ 我的项目,Solitude ]
cover: https://bu.dusays.com/2024/01/24/65b1121634de2.png
abbrlink: c33ba1e3
date: 2024-01-14 00:00:00
---

> 原主题内置的个性定位卡片，样式和信息太固定了，写个教程，方便大家自定义。

## 效果

默认效果，自定义可以参考下面的教程。

![效果](https://bu.dusays.com/2024/01/24/65b11c1bc63f1.png)

## 教程

{% fold v1教程，已弃用 %}
   1. 在 <strong>source</strong> 文件夹下找到 <strong>_data</strong> 文件夹（没有先新建），找到 <strong>aside.yml</strong> 文件（没有先新建）。在 <strong>aside.yml</strong> 文件中添加如下代码：
       ```yml
       home: # 如果在首页显示
           Sticky:
             - class_name: card-welcome
               id_name:
               name: 来访者
               icon: scoicon sco-map-pin-fill
               class_content:
               id_content: 'welcome-info'
       ```
   2. 获取Key、经度、纬度
      注册腾讯地图开发者账号，获取 <strong>Key</strong>，[点击前往](https://lbs.qq.com/)。
      ![注册腾讯地图开发者账号](https://bu.dusays.com/2024/01/24/65b11c3aeed08.png)
      创建应用，名字随意，类型选其他。[点击前往](https://lbs.qq.com/console/mykey.html)。
      ![创建应用](https://bu.dusays.com/2024/01/24/65b11c5392a60.png)
      创建Key，名字随意，类型选 <strong>WebServiceAPI</strong>，白名单写自己的域名（只需要顶级域名即可）。
      ![添加key](https://bu.dusays.com/2024/01/24/65b11c7b62c00.png)
      ![信息参考](https://bu.dusays.com/2024/01/24/65b11cab08395.png)
      还需在配额页面，将 <strong>IP定位</strong> 配置调用次数。
      ![配额页面](https://bu.dusays.com/2024/01/24/65b11cd02b9b6.png)
      获取经纬度，[点击前往](https://lbs.qq.com/tool/getpoint/index.html)。
      ![搜索自己的位置坐标，在右侧复制经（左）纬（右）度](https://bu.dusays.com/2024/01/24/65b11cf13b868.png)
   3. 在 <strong>source</strong> 文件夹下找到 <strong>js</strong> 文件夹（没有先新建），找到 <strong>custom.js</strong> 文件（没有先新建）。在 <strong>custom.js</strong> 文件中添加如下代码：
       ```js
       (function () {
       var longitude = '经度';
       var latitude = '纬度';
       var txkey = '腾讯地图Key';
       var ipLoacation;

       //请求数据
       ipLoacation = window.saveToLocal.get('ipLocation');
       if (!ipLoacation) {
           var script = document.createElement('script');
           var url = `https://apis.map.qq.com/ws/location/v1/ip?key=${txkey}&output=jsonp`;
           script.src = url;
           window.QQmap = function (data) {
               ipLoacation = data;
               // 将数据保存到 localStorage，过期时间设置为 1 天
               window.saveToLocal.set('ipLocation', ipLoacation, 1);
               document.body.removeChild(script);
               delete window.QQmap;
           };
           document.body.appendChild(script);
       }

       function getDistance(e1, n1, e2, n2) {
           const R = 6371
           const {sin, cos, asin, PI, hypot} = Math

           let getPoint = (e, n) => {
               e *= PI / 180
               n *= PI / 180
               return {x: cos(n) * cos(e), y: cos(n) * sin(e), z: sin(n)}
           }

           let a = getPoint(e1, n1)
           let b = getPoint(e2, n2)
           let c = hypot(a.x - b.x, a.y - b.y, a.z - b.z)
           let r = asin(c / 2) * 2 * R
           return Math.round(r);
       }

       function showWelcome() {
           let dist = getDistance(longitude, latitude, ipLoacation.result.location.lng, ipLoacation.result.location.lat); //这里换成自己的经纬度
           let pos = ipLoacation.result.ad_info.nation;
           let ip;
           let posdesc;
           //根据国家、省份、城市信息自定义欢迎语
           switch (ipLoacation.result.ad_info.nation) {
               case "日本":
                   posdesc = "よろしく，一起去看樱花吗";
                   break;
               case "美国":
                   posdesc = "Let us live in peace!";
                   break;
               case "英国":
                   posdesc = "想同你一起夜乘伦敦眼";
                   break;
               case "俄罗斯":
                   posdesc = "干了这瓶伏特加！";
                   break;
               case "法国":
                   posdesc = "C'est La Vie";
                   break;
               case "德国":
                   posdesc = "Die Zeit verging im Fluge.";
                   break;
               case "澳大利亚":
                   posdesc = "一起去大堡礁吧！";
                   break;
               case "加拿大":
                   posdesc = "拾起一片枫叶赠予你";
                   break;
               case "中国":
                   pos = ipLoacation.result.ad_info.province + " " + ipLoacation.result.ad_info.city + " " + ipLoacation.result.ad_info.district;
                   ip = ipLoacation.result.ip;
                   switch (ipLoacation.result.ad_info.province) {
                       case "北京市":
                           posdesc = "北——京——欢迎你~~~";
                           break;
                       case "天津市":
                           posdesc = "讲段相声吧";
                           break;
                       case "河北省":
                           posdesc = "山势巍巍成壁垒，天下雄关铁马金戈由此向，无限江山";
                           break;
                       case "山西省":
                           posdesc = "展开坐具长三尺，已占山河五百余";
                           break;
                       case "内蒙古自治区":
                           posdesc = "天苍苍，野茫茫，风吹草低见牛羊";
                           break;
                       case "辽宁省":
                           posdesc = "我想吃烤鸡架！";
                           break;
                       case "吉林省":
                           posdesc = "状元阁就是东北烧烤之王";
                           break;
                       case "黑龙江省":
                           posdesc = "很喜欢哈尔滨大剧院";
                           break;
                       case "上海市":
                           posdesc = "众所周知，中国只有两个城市";
                           break;
                       case "江苏省":
                           switch (ipLoacation.result.ad_info.city) {
                               case "南京市":
                                   posdesc = "这是我挺想去的城市啦";
                                   break;
                               case "苏州市":
                                   posdesc = "上有天堂，下有苏杭";
                                   break;
                               default:
                                   posdesc = "散装是必须要散装的";
                                   break;
                           }
                           break;
                       case "浙江省":
                           posdesc = "东风渐绿西湖柳，雁已还人未南归";
                           break;
                       case "河南省":
                           switch (ipLoacation.result.ad_info.city) {
                               case "郑州市":
                                   posdesc = "豫州之域，天地之中";
                                   break;
                               case "南阳市":
                                   posdesc = "臣本布衣，躬耕于南阳此南阳非彼南阳！";
                                   break;
                               case "驻马店市":
                                   posdesc = "峰峰有奇石，石石挟仙气嵖岈山的花很美哦！";
                                   break;
                               case "开封市":
                                   posdesc = "刚正不阿包青天";
                                   break;
                               case "洛阳市":
                                   posdesc = "洛阳牡丹甲天下";
                                   break;
                               default:
                                   posdesc = "可否带我品尝河南烩面啦？";
                                   break;
                           }
                           break;
                       case "安徽省":
                           posdesc = "蚌埠住了，芜湖起飞";
                           break;
                       case "福建省":
                           posdesc = "井邑白云间，岩城远带山";
                           break;
                       case "江西省":
                           posdesc = "落霞与孤鹜齐飞，秋水共长天一色";
                           break;
                       case "山东省":
                           posdesc = "遥望齐州九点烟，一泓海水杯中泻";
                           break;
                       case "湖北省":
                           switch (ipLoacation.result.ad_info.city) {
                               case "黄冈市":
                                   posdesc = "红安将军县！辈出将才！";
                                   break;
                               default:
                                   posdesc = "来碗热干面~";
                                   break;
                           }
                           break;
                       case "湖南省":
                           posdesc = "74751，长沙斯塔克";
                           break;
                       case "广东省":
                           switch (ipLoacation.result.ad_info.city) {
                               case "广州市":
                                   posdesc = "看小蛮腰，喝早茶了嘛~";
                                   break;
                               case "深圳市":
                                   switch (ipLoacation.result.ad_info.district) {
                                       case "坪山区":
                                           posdesc = "好巧！博主也在坪山区生活喔~";
                                           break;
                                       default:
                                           posdesc = "今天你996了嘛~";
                                           break;
                                   }
                                   break;
                               case "阳江市":
                                   posdesc = "阳春合水！博主家乡~ 欢迎来玩~";
                                   break;
                               default:
                                   posdesc = "来两斤福建人~";
                                   break;
                           }
                           break;
                       case "广西壮族自治区":
                           posdesc = "桂林山水甲天下";
                           break;
                       case "海南省":
                           posdesc = "朝观日出逐白浪，夕看云起收霞光";
                           break;
                       case "四川省":
                           posdesc = "康康川妹子";
                           break;
                       case "贵州省":
                           posdesc = "茅台，学生，再塞200";
                           break;
                       case "云南省":
                           posdesc = "玉龙飞舞云缠绕，万仞冰川直耸天";
                           break;
                       case "西藏自治区":
                           posdesc = "躺在茫茫草原上，仰望蓝天";
                           break;
                       case "陕西省":
                           posdesc = "来份臊子面加馍";
                           break;
                       case "甘肃省":
                           posdesc = "羌笛何须怨杨柳，春风不度玉门关";
                           break;
                       case "青海省":
                           posdesc = "牛肉干和老酸奶都好好吃";
                           break;
                       case "宁夏回族自治区":
                           posdesc = "大漠孤烟直，长河落日圆";
                           break;
                       case "新疆维吾尔自治区":
                           posdesc = "驼铃古道丝绸路，胡马犹闻唐汉风";
                           break;
                       case "台湾省":
                           posdesc = "我在这头，大陆在那头";
                           break;
                       case "香港特别行政区":
                           posdesc = "永定贼有残留地鬼嚎，迎击光非岁玉";
                           break;
                       case "澳门特别行政区":
                           posdesc = "性感荷官，在线发牌";
                           break;
                       default:
                           posdesc = "带我去你的城市逛逛吧！";
                           break;
                   }
                   break;
               default:
                   posdesc = "带我去你的国家逛逛吧";
                   break;
           }

           //根据本地时间切换欢迎语
           let timeChange;
           let date = new Date();
           if (date.getHours() >= 5 && date.getHours() < 11) timeChange = "<span class='welcome-time'>🌤️ 早上好，一日之计在于晨</span>";
           else if (date.getHours() >= 11 && date.getHours() < 13) timeChange = "<span class='welcome-time'>☀️ 中午好，记得午休喔~</span>";
           else if (date.getHours() >= 13 && date.getHours() < 17) timeChange = "<span class='welcome-time'>🕞 下午好，饮茶先啦！</span>";
           else if (date.getHours() >= 17 && date.getHours() < 19) timeChange = "<span class='welcome-time'>🚶‍♂️ 即将下班，记得按时吃饭~</span>";
           else if (date.getHours() >= 19 && date.getHours() < 24) timeChange = "<span class='welcome-time'>🌙 晚上好，夜生活嗨起来！</span>";
           else timeChange = "<span class='welcome-time'>夜深了，早点休息，少熬夜</span>";

           document.getElementById("welcome-info").innerHTML =
               `<span>热烈欢迎来自~</span><br><span><span style="color: var(--sco-main);font-weight: bold;">${pos}</span> 的朋友</span><br><span class="welcome-message">${posdesc}</span><br>您当前位置距博主约 <b><span style="color: var(--sco-main);font-weight: bold;">${dist}</span></b> 公里！<br><span style="word-wrap:break-word">您的IP地址为：${ip}</span><br>${timeChange}`;
       }

       const isWelcome = () => document.getElementById("welcome-info") && showWelcome();

       isWelcome();
       document.addEventListener('pjax:complete', isWelcome);
       })();
       ```
      将其中的 <strong>经度</strong>、<strong>纬度</strong>、<strong>腾讯地图Key</strong> 替换成自己的即可。
   4. 自定义
      自定义欢迎语，可以参考下面的代码：
      ipLoacation.result.ad_info.nation：国家，其中内部的`posdesc`为国家欢迎语。
      ipLoacation.result.ad_info.province：省份，其中内部的`posdesc`为省份欢迎语。
      ipLoacation.result.ad_info.district：城市，其中内部的`posdesc`为城市欢迎语。
      根据演示配置，可以自定义欢迎语，例如：
      ```js
      switch (ipLoacation.result.ad_info.province) {
        case "湖南省":
            switch (ipLoacation.result.ad_info.city) {
                case "衡阳市":
                    posdesc = "衡阳人民欢迎你！";
                    break;
                default:
                    posdesc = "带我去你的城市逛逛吧！";
                    break;
      ```
      自定义样式，可以直接给内容的样式增加内联样式。
{% endfold %}

> v2教程使用<b>青桔-API</b>，不需要申请Key，但是有频率限制。

1. 在 <strong>source</strong> 文件夹下找到 <strong>_data</strong> 文件夹（没有先新建），找到 <strong>aside.yml</strong> 文件（没有先新建）。在 <strong>aside.yml</strong> 文件中添加如下代码：
    ```yml
    home: # 如果在首页显示
        Sticky:
          - class_name: card-welcome
            id_name:
            name: 来访者
            icon: scoicon sco-map-pin-fill
            class_content:
            id_content: 'welcome-info'
    ```
2. 在 <strong>source</strong> 文件夹下找到 <strong> css</strong> 文件夹（没有先新建），找到 <strong>custom.css</strong> 文件（没有先新建）。在 <strong>custom.css</strong> 文件中添加如下代码：
   ```css
   #aside-content .card-welcome{
        padding: .4rem .6rem;
    }
    
    #aside-content .card-welcome #welcome-info{
        padding: 0 .4rem;
        font-size: .8rem;
    }
    
    #aside-content .card-welcome #welcome-info .ip{
        user-select: all;
        border-radius: 10px;
        background-color: var(--sco-main);
        word-wrap: break-word;
        color: var(--sco-main);
        box-shadow: 0 0 3px var(--sco-main-op);
        padding: 2px 4px;
        transition: all .3s ease-in-out;
    }
    
    #aside-content .card-welcome #welcome-info .ip:hover{
        color: var(--sco-card-bg);
    }
   ```
3. 在 <strong>source</strong> 文件夹下找到 <strong>js</strong> 文件夹（没有先新建），找到 <strong>custom.js</strong> 文件（没有先新建）。在 <strong>custom.js</strong> 文件中添加如下代码：
   ```js
   (function () {
    const lng = '112.8455033596802'; // 经度
    const lat = '26.430308353457896'; // 纬度
    let ipStore = saveToLocal.get('location');

    (async function () {
        if (!ipStore) {
            await fetch(`https://api.qjqq.cn/api/Local`)
                .then(res => res.json())
                .then(data => {
                    if (data.code === "Success") {
                        ipStore = data;
                        saveToLocal.set('location', ipStore, 3600 * 24);
                        showWelcome();
                    }
                })
                .catch(err => console.log(err));
        }
    })()

    function getDistance(e1, n1, e2, n2) {
        const R = 6371
        const {sin, cos, asin, PI, hypot} = Math

        let getPoint = (e, n) => {
            e *= PI / 180
            n *= PI / 180
            return {x: cos(n) * cos(e), y: cos(n) * sin(e), z: sin(n)}
        }

        let a = getPoint(e1, n1)
        let b = getPoint(e2, n2)
        let c = hypot(a.x - b.x, a.y - b.y, a.z - b.z)
        let r = asin(c / 2) * 2 * R
        return Math.round(r);
    }

    function showWelcome() {
        let dist = getDistance(lng, lat, ipStore.data.lng, ipStore.data.lat); //这里换成自己的经纬度
        let pos = ipStore.data.continent;
        let ip = ipStore.ip || "未知";
        let posdesc;
        //根据国家、省份、城市信息自定义欢迎语
        switch (ipStore.data.country) {
            case "日本":
                posdesc = "よろしく，一起去看樱花吗";
                break;
            case "美国":
                posdesc = "Let us live in peace!";
                break;
            case "英国":
                posdesc = "想同你一起夜乘伦敦眼";
                break;
            case "俄罗斯":
                posdesc = "干了这瓶伏特加！";
                break;
            case "法国":
                posdesc = "C'est La Vie";
                break;
            case "德国":
                posdesc = "Die Zeit verging im Fluge.";
                break;
            case "澳大利亚":
                posdesc = "一起去大堡礁吧！";
                break;
            case "加拿大":
                posdesc = "拾起一片枫叶赠予你";
                break;
            case "中国":
                pos = ipStore.data.prov + " " + ipStore.data.city + " " + ipStore.data.district;
                switch (ipStore.data.prov) {
                    case "北京市":
                        posdesc = "北——京——欢迎你~~~";
                        break;
                    case "天津市":
                        posdesc = "讲段相声吧";
                        break;
                    case "河北省":
                        posdesc = "山势巍巍成壁垒，天下雄关铁马金戈由此向，无限江山";
                        break;
                    case "山西省":
                        posdesc = "展开坐具长三尺，已占山河五百余";
                        break;
                    case "内蒙古自治区":
                        posdesc = "天苍苍，野茫茫，风吹草低见牛羊";
                        break;
                    case "辽宁省":
                        posdesc = "我想吃烤鸡架！";
                        break;
                    case "吉林省":
                        posdesc = "状元阁就是东北烧烤之王";
                        break;
                    case "黑龙江省":
                        posdesc = "很喜欢哈尔滨大剧院";
                        break;
                    case "上海市":
                        posdesc = "众所周知，中国只有两个城市";
                        break;
                    case "江苏省":
                        switch (ipStore.data.city) {
                            case "南京市":
                                posdesc = "这是我挺想去的城市啦";
                                break;
                            case "苏州市":
                                posdesc = "上有天堂，下有苏杭";
                                break;
                            default:
                                posdesc = "散装是必须要散装的";
                                break;
                        }
                        break;
                    case "浙江省":
                        posdesc = "东风渐绿西湖柳，雁已还人未南归";
                        break;
                    case "河南省":
                        switch (ipStore.data.city) {
                            case "郑州市":
                                posdesc = "豫州之域，天地之中";
                                break;
                            case "南阳市":
                                posdesc = "臣本布衣，躬耕于南阳此南阳非彼南阳！";
                                break;
                            case "驻马店市":
                                posdesc = "峰峰有奇石，石石挟仙气嵖岈山的花很美哦！";
                                break;
                            case "开封市":
                                posdesc = "刚正不阿包青天";
                                break;
                            case "洛阳市":
                                posdesc = "洛阳牡丹甲天下";
                                break;
                            default:
                                posdesc = "可否带我品尝河南烩面啦？";
                                break;
                        }
                        break;
                    case "安徽省":
                        posdesc = "蚌埠住了，芜湖起飞";
                        break;
                    case "福建省":
                        posdesc = "井邑白云间，岩城远带山";
                        break;
                    case "江西省":
                        posdesc = "落霞与孤鹜齐飞，秋水共长天一色";
                        break;
                    case "山东省":
                        posdesc = "遥望齐州九点烟，一泓海水杯中泻";
                        break;
                    case "湖北省":
                        switch (ipStore.data.city) {
                            case "黄冈市":
                                posdesc = "红安将军县！辈出将才！";
                                break;
                            default:
                                posdesc = "来碗热干面~";
                                break;
                        }
                        break;
                    case "湖南省":
                        switch (ipStore.data.city) {
                            case "长沙市":
                                posdesc = "长沙斯塔克";
                                break;
                            case "岳阳市":
                                posdesc = "岳阳楼记";
                                break;
                            case "衡阳市":
                                posdesc = "大美雁城欢迎您！";
                                switch (ipStore.data.district) {
                                    case "南岳区":
                                        posdesc = "南岳衡山，五岳之首";
                                        break;
                                    case "耒阳市":
                                        posdesc = "千年纸都欢迎您！";
                                        break;
                                    default:
                                        break;
                                }
                                break;
                            default:
                                posdesc = "湖南人民好客，欢迎来湖南旅游";
                                break;
                        }
                        break;
                    case "广东省":
                        switch (ipStore.data.city) {
                            case "广州市":
                                posdesc = "看小蛮腰，喝早茶了嘛~";
                                break;
                            case "深圳市":
                                switch (ipStore.data.district) {
                                    case "坪山区":
                                        posdesc = "好巧！博主也在坪山区生活喔~";
                                        break;
                                    default:
                                        posdesc = "今天你996了嘛~";
                                        break;
                                }
                                break;
                            case "阳江市":
                                posdesc = "阳春合水！博主家乡~ 欢迎来玩~";
                                break;
                            default:
                                posdesc = "来两斤福建人~";
                                break;
                        }
                        break;
                    case "广西壮族自治区":
                        posdesc = "桂林山水甲天下";
                        break;
                    case "海南省":
                        posdesc = "朝观日出逐白浪，夕看云起收霞光";
                        break;
                    case "四川省":
                        posdesc = "康康川妹子";
                        break;
                    case "贵州省":
                        posdesc = "茅台，学生，再塞200";
                        break;
                    case "云南省":
                        posdesc = "玉龙飞舞云缠绕，万仞冰川直耸天";
                        break;
                    case "西藏自治区":
                        posdesc = "躺在茫茫草原上，仰望蓝天";
                        break;
                    case "陕西省":
                        posdesc = "来份臊子面加馍";
                        break;
                    case "甘肃省":
                        posdesc = "羌笛何须怨杨柳，春风不度玉门关";
                        break;
                    case "青海省":
                        posdesc = "牛肉干和老酸奶都好好吃";
                        break;
                    case "宁夏回族自治区":
                        posdesc = "大漠孤烟直，长河落日圆";
                        break;
                    case "新疆维吾尔自治区":
                        posdesc = "驼铃古道丝绸路，胡马犹闻唐汉风";
                        break;
                    case "台湾省":
                        posdesc = "我在这头，大陆在那头";
                        break;
                    case "香港特别行政区":
                        posdesc = "永定贼有残留地鬼嚎，迎击光非岁玉";
                        break;
                    case "澳门特别行政区":
                        posdesc = "性感荷官，在线发牌";
                        break;
                    default:
                        posdesc = "带我去你的城市逛逛吧！";
                        break;
                }
                break;
            default:
                posdesc = "带我去你的国家逛逛吧";
                break;
        }

        let timeChange;
        let date = new Date();
        if (date.getHours() >= 5 && date.getHours() < 11) timeChange = "<span class='welcome-time'>🌤️ 早上好，一日之计在于晨</span>";
        else if (date.getHours() >= 11 && date.getHours() < 13) timeChange = "<span class='welcome-time'>☀️ 中午好，记得午休喔~</span>";
        else if (date.getHours() >= 13 && date.getHours() < 17) timeChange = "<span class='welcome-time'>🕞 下午好，饮茶先啦！</span>";
        else if (date.getHours() >= 17 && date.getHours() < 19) timeChange = "<span class='welcome-time'>🚶‍♂️ 即将下班，记得按时吃饭~</span>";
        else if (date.getHours() >= 19 && date.getHours() < 24) timeChange = "<span class='welcome-time'>🌙 晚上好，夜生活嗨起来！</span>";
        else timeChange = "<span class='welcome-time'>夜深了，早点休息，少熬夜</span>";

        document.getElementById("welcome-info").innerHTML =
            `<span>热烈欢迎来自~</span><br><b>${pos}</b> 的朋友</span><br><b>${posdesc}</b><br>您当前位置距博主约 <b>${dist}</b> 公里！<br><span>您的IP地址为：<b class="ip">${ip}</b></span><br>${timeChange}`;
    }

    const isWelcome = () => document.getElementById("welcome-info") && showWelcome();

    isWelcome();
    document.addEventListener('pjax:complete', isWelcome);
   })();
   ```
   - 只需把其中的经度、纬度替换成自己的即可。
   - 获取经纬度，[点击前往](https://lbs.qq.com/tool/getpoint/index.html)。
   ![搜索自己的位置坐标，在右侧复制经（左）纬（右）度](https://bu.dusays.com/2024/01/24/65b11cf13b868.png)
4. 自定义
   根据演示配置，可以自定义欢迎语，例如：
      ```js
        switch (ipStore.data.prov) {
            case "湖南省":
                switch (ipStore.data.city) {
                    case "长沙市":
                        posdesc = "长沙斯塔克";
                        break;
                    case "岳阳市":
                        posdesc = "岳阳楼记";
                        break;
                    case "衡阳市":
                        posdesc = "大美雁城欢迎您！";
                        switch (ipStore.data.district) {
                            case "南岳区":
                                posdesc = "南岳衡山，五岳之首";
                                break;
                            case "耒阳市":
                                posdesc = "千年纸都欢迎您！";
                                break;
                            default:
                                break;
                        }
                break;
      ```
   - 自定义样式，根据自己的要求修改即可。