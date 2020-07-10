一、什么是User-Agent

User-Agent中文名为用户代理，简称 UA，是Http协议中的一部分，属于头域的组成部分，它是一个特殊字符串头，使得服务器能够识别客户使用的操作系统及版本、CPU 类型、浏览器及版本、浏览器渲染引擎、浏览器语言、浏览器插件等。在网络请求当中，User-Agent 是标明身份的一种标识，通过这个标识，用户所访问的网站可以显示不同的排版从而为用户提供更好的体验或者进行信息统计；例如用手机访问谷歌和电脑访问是不一样的，这些是谷歌根据访问者的UA来判断的。UA可以进行伪装。

二、常见User-Agent介绍

浏览器UA 字串的标准格式为： 浏览器标识 (操作系统标识; 加密等级标识; 浏览器语言) 渲染引擎标识 版本信息

常见的解析如下：

Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/36.0.1985.125 Safari/537.36 
Mozilla/5.0 ：以前用于Netscape浏览器，目前大多数浏览器UA都会带有

Windows NT 6.1：代表windows7系统

WOW64：Windows-on-Windows 64-bit，32位的应用程序运行于此64位处理器上

AppleWebKit/537.36：浏览器内核

KHTML：一个HTML排版引擎

like Gecko：这不是Geckeo 浏览器，但是运行起来像Geckeo浏览器

Chrome/36.0.1985.125：Chrome版本号

Safari/537.36：因为AppleWebKit渲染引擎是苹果公司开发的，而Google公司要采用它，为了获得服务器端的正确响应，就进行伪装。

关于Safari/537.36有个好玩的事情，各个浏览器互相伪装

Apple开发了Safari，使用了KHTML，同时也增加了很多新特性，后来另起炉灶叫了WebKit，但是它有希望能够看到那些为KHTML编写的网页，于是Safari标称自己为Mozilla/5.0 (Macintosh; U; PPC Mac OS X; de-de) AppleWebKit/85.7 (KHTML, like Gecko) Safari/85.5

Google也开发了自己的浏览器Chrome，使用了Webkit，有点像Safari，希望能看到为Safari编写的网页，于是决定装成Safari。Chrome使用了WebKit渲染引擎，想装成Safari，Chrome宣称自己是Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US) AppleWebKit/525.13 (KHTML, like Gecko)Chrome/0.2.149.27 Safari/525.13

常见UA如下：

PC：

Chrome浏览器：
Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_3) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/64.0.3282.186 Safari/537.36
Safari浏览器：
Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_3) AppleWebKit/604.5.6 (KHTML, like Gecko) Version/11.0.3 Safari/604.5.6
Firefox浏览器：
Mozilla/5.0 (Macintosh; Intel Mac OS X 10.13; rv:58.0) Gecko/20100101 Firefox/58.0
QQ浏览器：
Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_3) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/60.0.3112.101 Safari/537.36 QQBrowser/4.3.4986.400
Edge浏览器：
Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/42.0.2311.135 Safari/537.36 Edge/13.10586
IE11：
Mozilla/5.0 (Windows NT 6.3; Win64, x64; Trident/7.0; rv:11.0) like Gecko
IE10：
Mozilla/5.0 (compatible; MSIE 10.0; Windows NT 6.2; Win64; x64; Trident/6.0)
MOBILE:

Safari浏览器：
Mozilla/5.0 (iPhone; CPU iPhone OS 11_2_6 like Mac OS X) AppleWebKit/604.5.6 (KHTML, like Gecko) Version/11.0 Mobile/15D100 Safari/604.1
Chrome浏览器：
Mozilla/5.0 (iPhone; CPU iPhone OS 11_2_6 like Mac OS X) AppleWebKit/604.1.34 (KHTML, like Gecko) CriOS/64.0.3282.112 Mobile/15D100 Safari/604.1
QQ内置浏览器：
Mozilla/5.0 (iPhone; CPU iPhone OS 11_2_6 like Mac OS X) AppleWebKit/604.5.6 (KHTML, like Gecko) Mobile/15D100 QQ/7.5.0.407 V1_IPH_SQ_7.5.0_1_APP_A Pixel/750 Core/UIWebView Device/Apple(iPhone 7) NetType/WIFI QBWebViewType/1
QQ浏览器：
Mozilla/5.0 (iPhone 91; CPU iPhone OS 11_2_6 like Mac OS X) AppleWebKit/604.5.6 (KHTML, like Gecko) Version/11.0 MQQBrowser/8.0.2 Mobile/15D100 Safari/8536.25 MttCustomUA/2 QBWebViewType/1 WKType/1
UC浏览器：
Mozilla/5.0 (iPhone; CPU iPhone OS 11_2_6 like Mac OS X; zh-CN) AppleWebKit/537.51.1 (KHTML, like Gecko) Mobile/15D100 UCBrowser/11.8.8.1060 Mobile AliApp(TUnionSDK/0.1.20.2)
WeChat内置浏览器：
Mozilla/5.0 (iPhone; CPU iPhone OS 11_2_6 like Mac OS X) AppleWebKit/604.5.6 (KHTML, like Gecko) Mobile/15D100 MicroMessenger/6.6.3 NetType/WIFI Language/zh_CN
Baidu浏览器：
Mozilla/5.0 (iPhone; CPU iPhone OS 11_2_6 like Mac OS X) AppleWebKit/604.5.6 (KHTML, like Gecko) Version/11. Mobile/15D100 Safari/600.1.4 baidubrowser/4.13.0.16 (Baidu; P2 11.2.6)
Sougou浏览器：
Mozilla/5.0 (iPhone; CPU iPhone OS 11_2_6 like Mac OS X) AppleWebKit/604.5.6 (KHTML, like Gecko) Mobile/15D100 SogouMobileBrowser/5.11.10
Weibo内置浏览器：
Mozilla/5.0 (iPhone; CPU iPhone OS 11_2_6 like Mac OS X) AppleWebKit/604.5.6 (KHTML, like Gecko) Mobile/15D100 Weibo (iPhone9,1__weibo__8.2.0__iphone__os11.2.6)

三、UA价值分析

1.用来识别是否爬虫：

User-Agent值是用来帮助服务器识别用户使用的操作系统、浏览器、浏览器版本等等信息的，因此也常被用来检测爬虫。许多网站会ban掉来自爬虫的请求，来达到反爬的目的。

正常浏览器的User-Agent值为：Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:62.0) Gecko/20100101 Firefox/62.0
使用requests时的默认User-Agent为：python-requests/2.18.4
scrapy的默认值为：Scrapy/1.5.0 (+https://scrapy.org)
服务器可以轻易识别出该请求是否来自爬虫。因此为了减小爬虫被ban的几率，我们可以通过设置请求的User-Agent来达到欺骗服务器的目的。

2.用来判断是否虚假设备：

UA是用户的一种标识，带有浏览器设备等信息，但是UA信息可以篡改，如果某一时间某一地域大批量UA聚集或者说UA标识信息和设备信息不同，可以细分查看是否是虚假设备。

本文转自 https://zhuanlan.zhihu.com/p/97973031
