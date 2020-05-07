本文是一个微成熟小白对于科学上网的一些切身感受的整理，自己捋思路，同时也为方便他人。顺便会不断更新一些实用资源、工具等。发现错误的地方欢迎斧正。正文中点击“回到顶部”四个字即可回到目录，点击目录也会跳到相应模块。<br>
`2020年4月28日更新：添加STC机场重要升级通知`<br>
* [一、国内网络基本了解](#一国内网络基本了解)<br>
* [二、科学上网](#二科学上网)<br>
  * [No1、没落的“VPN”](#没落的VPN)<br>
    * [什么是VPN](#1-什么是VPN )<br>
    * [VPN现状](#2-VPN现状)<br>
  * [No2、关于机场](#关于机场)<br>
    * [什么是机场](#1-什么是机场)<br>
    * [机场的选择](#2-机场的选择)<br>
      * [技术层面](#技术层面)<br>
        * [BGP中转和IPLC的通俗理解](#bgp中转和iplc的通俗理解)<br>
      * [主观层面](#主观层面)<br>
        * [机场的外观设计](#机场的外观设计)<br>
        * [机场电报群观察交流](#机场电报群观察交流)<br>
        * [机场的测速](#机场的测速)<br>
        * [机场价格](#机场价格)<br>
* [三、我的机场推荐及使用感受](#三我的机场推荐及使用感受)<br>
  * [SSR、V2ray机场：STC](#ssrv2ray机场stc官网)
  * [Trojan机场](#trojan机场shadowsocks官网)
  * [机场综合使用感受](#机场综合使用感受)
* [四、主流科学上网工具下载(包含Win、Mac、Android三大平台)](#四主流科学上网工具下载包含winmacandroid三大平台)<br>
  * [Shadowsocks](#Shadowsocks简称SS)
  * [ShadowsocksR](#ShadowsocksR简称SSR)
  * [V2ray(含官方使用手册)](#V2ray简称V2)
  * [clash(含CFW使用说明书)](#clash)
    * [ClashR汉化版，支持SSR和V2订阅](#clash)  
  * [Trojan](#Trojan)
  * [Mellow](#Mellow)<br>
  * [Netch(Win)](#netch)<br>
  * [Pharos Pro(Android)](#pharos-pro)<br>
  * [shadowrocket基础教程及分组规则自动切换节点](#shadowrocket)<br>
* [五、其它实用资源、工具](#五其它实用资源工具)
***

# 一、国内网络基本了解
大家都知道，我们中国对网络的限制比较严格，不是所有的网站咱们都能浏览。国家主要通过GFW([dns劫持](https://baike.baidu.com/item/%E5%9F%9F%E5%90%8D%E5%8A%AB%E6%8C%81/7657893?fromtitle=DNS%E5%8A%AB%E6%8C%81&fromid=6739044&fr=aladdin)、[dns污染](https://baike.baidu.com/item/DNS%E6%B1%A1%E6%9F%93)和[ip封锁](https://baike.baidu.com/item/ip%E5%B0%81%E9%94%81)等手段)进行网络封锁。下图是百度百科对GFW（俗称“墙”）的介绍
![GFW](https://www.louimg.com/u/20200312/11050110.png "GFW的介绍")
大家主要看红圈里的文字，GFW的功劳：让国民政治觉悟提升了不少，所以GFW只会越来越完善。但对于大多数网民来说，网络是我们学习、工作、美好生活的重要工具，GFW一定程度上把好多对我们学习、工作有帮助的综合性很强的技术、学术网站、社交网站等也拒之门外。
<br>大家经常听说的网站如[油管YouTube](https://www.youtube.com)、[脸书Facebook](https://www.facebook.com/)、[推特Twitter](https://twitter.com)、[电报telegram](https://telegram.org/)、[谷歌google](https://www.google.com.hk/)、[维基百科](https://zh.wikipedia.org/)等，这些我们都是无法正常访问的。需要科学上网（俗称翻墙）才能上。所以，这种背景下，也就出现了各种各样的突破GFW限制的工具，突破网络审查的软件通常被称作翻墙软件，俗称梯子。翻墙软件并不只是大家理解的VPN软件，还有基于其它协议的代理软件。<br>[回到顶部](#readme)
***

# 二、科学上网
## 没落的“VPN”
#### 1. 什么是VPN 
VPN全称“虚拟私人网络（Virtual Private Network）”，VPN是一个统称。VPN是一种加密通讯技术，它被设计出来的目的是数据传输安全和网络匿名。所以它不是为了翻墙而生的，维基百科里关于VPN的介绍，说它的特殊使用才是翻墙。它的出现远早于GFW。
![VPN](https://www.louimg.com/u/20200312/15453995.png "VPN的维基介绍")
GFW机制加上劳动人民的无穷智慧，促使聪慧的劳动人民开始用VPN连接外国网络实现翻墙，随着使用人数的激增和网络环境的发展，商业化的一键VPN也逐渐成熟，一些免费VPN和付费VPN就这样诞生了。<br>[回到顶部](#readme)
#### 2. VPN现状
使用VPN，不足之处在于数据分流不灵活，会将开启了VPN的设备的所有数据流量全部导向至VPN服务器上；另外如果VPN服务器上有流量监视软件运行，那么用户所传输的数据将有信息安全威胁；进一步来说，由于VPN设计的初衷并不是用于翻墙，因此数据流量的特征非常明显，容易引起审查机构注意，导致被封。所以，VPN这种翻墙方式基本已经没落了。但是市场上还是有一些一键VPN软件，它们背后的原理其实已经背离了VPN的真正原理，这些一键VPN其实就是把一些机场节点融合到了自己的APP，所以现在好多得VPN其实也不算真正的VPN了。至于免费的VPN，由于用户人数与流量众多，常会暴露出了公共网络服务的特质，所以经常会被封，而且VPN也存在后台钓鱼的风险，虽然可能现在这种情况好多了（谁知道呢），但是之前毕竟存在过，所以本人主观上严重不建议长期使用这种一键VPN软件。<br>
VPN作为过去很长一段时间最主流最热门最常用最为人所知的翻墙手段，已然成为翻墙的代名词。即便是VPN已不再常用的今天，当人们谈及翻墙的时候，说得最多的仍是：“你有什么好用的vpn吗？”<br>
[回到顶部](#readme)<br>
***

## 关于[机场](https://t.co/OGzuQ1kAL3?amp=1)
### 1. 什么是[机场](https://t.co/OGzuQ1kAL3?amp=1)
随着VPN的没落，现在主流的科学上网方式是大家经常听的SS（Shadowsocks）、ssr（ShadowsocksR）、V2(v2ray)、Trojan等等这些代理工具，还有基于这些代理工具的原理，扩展衍生出的在各平台使用且支持以上几种翻墙协议的科学上网工具，如clash、shadowrocket、Quantumult、Pharos Pro等等非常多。<br>
这些工具的统一特点就是：工具自身没有翻墙功能，需要自行在服务端和客户端上部署，优点就是更加安全、速度更快，看似比一键VPN方法“繁琐”，但实际操作非常简单，其中服务端的部署有两种情况：<br>
第一种是我们自己购买vps部署，这就是人们常说的我自己搭建节点，喜欢折腾的伙伴可以自己去购买vps搭建，网上教程非常多<br>
第二种，就是有人替我们部署好了，直接用就可以。这也是目前用的最多的科学上网方式，提供这项服务的就是[机场](https://t.co/OGzuQ1kAL3?amp=1)。<br>
服务端部署好后，我们只需将服务器地址、端口这些基本信息添加到我们电脑或手机上的代理工具里，这就是客户端部署，这就实现了科学上网。现在很多工具都支持一键订阅，多数机场也提供了订阅链接，不需要我们手动逐一添加节点。<br>[回到顶部](#readme)
### 2. [机场](https://t.co/fdfliso9wM?amp=1)的选择
#### 技术层面
##### BGP中转和IPLC的通俗理解
大家在购买机场时候，会经常见到BGP中转、IPLC专线这些名词。至于他们的专业意义，自行google查询。对于很多不是专业研究这个的伙伴，就算我们查询了，也可能是似懂非懂的状态，所以这里不会给大家去深挖那些专业概念，我们尽量从小白角度出发，明白他们的所起的作用就行。<br>
首先，我们要了解的就是我们的电脑、手机通过机场翻墙，数据经历了一个什么过程，大致有以下几种类型（从专业角度讲，有些地方可能不是很恰当，但很形象）：
* 直连<br>
  * 用户 -> ss、ssr等协议 -> 公网传输穿过GFW -> 国外服务器<br>
大多数机场节点都是这种，尤其是一些免费节点。此方式成本低，因为是协议直接过GFW，虽然协议本身也做了技术处理，但大流量还是很容易被GFW识别，这也就是为什么有的机场节点经常会出现不稳定现象，或者干脆就被封不能用了。而且公网传输，使用人多，流量拥挤就会速度变慢。<br>
好点的机场主可能会单独购买一条线路，这也就是我们说的独享线路机场，速度还稍微快点。有些功利性的机场主会租一条线路，意味着这一条线路同时被租给N个机场，这是我们常说的共享线路机场，速度和稳定性就得碰运气了。<br>[回到顶部](#readme)
* 公网中转（BGP中转）<br>
  * 用户 -> ss、ssr等协议 -> 国内中转服务器 -> 公网穿过GFW ->  国外服务器<br>
中转服务器到GFW这一段，一般会使用一些隧道协议，以实现负载均衡、高可用、防止被墙等效果，且对传输速度也做了优化。但是加BGP中转是比较昂贵的，所以能发现机场中带BGP中转的节点价格会比普通节点的价格贵。
* 专线内网中转（IPLC）<br>
  * 用户 -> ss、ssr等协议 -> 专线服务器A（自带中转功能）-> 内网传输 -> 国外专线服务器B<br>
这种方式你会发现，少了一个环节，就是它没有过GFW，就是传说中的不会被墙，因为它压根就不过墙，而且是点对点直接传输，速度也是最快的。但是加IPLC比加BGP的价格更贵，所以你会发现，机场节点中带IPLC的也是卖的最贵的。目前国内大多的IPLC线都是采用的阿里内网线路，严格来说，不能算的上真正的IPLC。也有真正的IPLC线路，比较少，从商人角度来说，除非能回本儿，否则搞真正的IPLC是不划算的。<br>[回到顶部](#readme)
#### 主观层面
除了技术层面，我们选择一个机场就是靠我们的主观判断，我个人是从以下几个方面判断的，只能供大家参考，不是绝对正确，毕竟这个行业鱼龙混杂，只要不怕担风险，是个人就可以开机场去捞金，水也较深。<br>
##### 机场的外观设计
大家会发现，几乎所有机场的界面布局都长得差不多，那是因为99%的机场用的模板代码都是同一套代码，细心的话，进机场的网站，看右下角（一般在右下，也有可能在左下），都有个staff的标志，没有staff的，会有SSPANEL，点进去也会看到staff。所以怎么去设计更换更精美的皮肤，也能侧面反映出机场主的用心程度。
##### 机场电报群观察交流
大多数的机场都会提供电报群链接，机场主一般也会在里边，购买前可进电报群，肯定会有用过的人对机场的优点问题等进行交流，也可从机场主日常在群中的活跃程度、答疑解惑、日常交流等方面去感受一个机场主是否真正用心在建设这个机场。<br>[回到顶部](#readme)
##### 机场的测速
有些机场有试用，可试用测速。但个人建议测速的话，可以先尝试按流量去购买机场的服务，一般1G也就不到1元，管够测速使用了。这里建议测试分多个时间段去测，再把每个时间段的测速结果去做个平均，看是否满足你心理预期。多数人喜欢用YouTube测速，其实YouTube测速只能做个参考，想得到更精确的数据，还是用SPEEDTEST或FAST测，测速时候开启全局代理，把其它会走代理的程序全部关闭。
##### 机场价格
这个其实不好评判，因为每个人心理的标准都不一样，个人感觉，只要体验感和机场的价格对称就行。没有哪个贵，哪个便宜之说，都是相对的。要根据自己的实际需求去购买，这跟咱们平时买车一样，好车就是体验好，但价格也不便宜。<br>

综述，个人认为主观方面的判断有时候可能比技术层面更重要，机场速度再快，再稳定，如果一段时间就跑路了，那还是掉坑了，所以我更看重主观层面的判断。因我自己也买过跑路的机场，身边很多朋友、网友也跟我说被坑过，所以非常看重这方面。<br>[回到顶部](#readme)
# 三、我的[机场](https://t.co/OGzuQ1kAL3?amp=1)推荐及使用感受
## SSR、V2ray机场：STC，[官网](https://t.co/OGzuQ1kAL3?amp=1)
[STC机场](https://t.co/fdfliso9wM?amp=1)，官网需要科学上网才能打开，用了将近一年半时间，我经历了三次机场升级，给我的体验感也由一般过渡到还行再到现在的好。也跟机场主聊过，去提一些建议，服务质量与价格还算对等。每次升级都是在大多客户反馈高峰期体验感不好的时候去考虑升级，去扩充升级一些设备，以带来更好的体验感。这也是**我看中的第一点**。毕竟它是从客户角度出发去考虑的，符合我上边说的主观层面判断，所以一直坚持用到现在。<br>
唯一可能不友好的一点就是价格也在随着升级在上涨，我觉得这个也可以理解，毕竟服务成本也在提高。**我看中的第二点**就是：涨价是不针对老客户的，就是你买了之后，不管以后机场涨价多少次，你永远都可用原来的价格去续费。还有，看YouTube4K视频、Netflix等视频网站没有任何问题。也可以去看一下[毒药大佬关于STC的测评](https://www.duyaoss.com/archives/1673/)。<br>
**STC机场支持订阅的工具如下图**
![stc订阅](https://www.nsaimg.com/2020/04/23/29e01443b25ec.jpg "stc订阅")
**STC机场在4月28日又一革命性升级：将旗舰和企业两个等级的全部线路升级为IPLC，具体见下图**
![stc升级](https://www.nsaimg.com/2020/04/28/501da8307ef19.jpg "stc升级")<br>
[回到顶部](#readme)
## Trojan机场：shadowsocks，[官网](https://t.co/FEE38PDhE6?amp=1)
官网需要科学上网才能打开，原来的老牌shadowsocks机场，在2020年2月份所有节点全部升级为Trojan，也是为了规避GFW，目前机场的名字还叫shadowsocks。这个机场我是从2015年开始使用，升级之后速度和稳定性都有了很大提升,下图是该机场在3月21日给客户发的邮件和我的购买账单，从服务升级到补差价，感觉也是从客户角度出发在考虑做更好的服务。<br>
![Trojan机场](https://www.louimg.com/u/20200323/15163186.jpg "Trojan机场")
![Trojan机场](https://www.louimg.com/u/20200329/10211993.png "Trojan机场")
**Trojan机场支持订阅的工具如下图**
![Trojan机场](https://www.nsaimg.com/2020/04/23/fb6508b7ece3e.jpg "Trojan机场")<br>
[回到顶部](#readme)
## 机场综合使用感受
* 我是用的移动300M宽带，平时翻墙会看Netflix和YouTube多点，而且经常会下载一些视频资源，两个机场配合使用完全能满足我的日常需求，用起来的区别就是：
  * 在一些高峰时段，Trojan机场看YouTube4K偶尔会出现卡顿，但看1080P还是没什么问题的。STC看4K几乎不卡、但看8K偶尔也会出现卡顿。<br>
  * 下载视频时候，下载工具IDM，按照我的带宽，STC是完全秒杀Trojan机场的，STC的下载速度平均下来能达到3M-5M不等,但Trojan机场的下载速度平均下来只有1M-2M不等。<br>
  * 当然STC的价格也比Trojan机场的价格高出很多。STC的基础套餐`每月38元`，还有其它的更高等级套餐，可自行到官网查看。Trojan机场的价格是`每年19.95AUD`（按现在汇率折合人民币86元）。价格标准请以机场官网最新价格为准。<br>
### 以上机场的使用教程见各自官网的帮助中心，各平台工具的配置步骤都非常详细。
  
[回到顶部](#readme)
***

<details>
  <summary># 四、主流科学上网工具下载(包含Win、Mac、Android三大平台)</summary>
</details>

# 四、主流科学上网工具下载(包含Win、Mac、Android三大平台)
## Shadowsocks（简称SS）
* [Shadowsocks（Win）](https://github.com/shadowsocks/shadowsocks-windows/releases)<br>
* [Shadowsocks（Mac）](https://github.com/shadowsocks/ShadowsocksX-NG/releases/)<br>
* [Shadowsocks（Android）](https://github.com/shadowsocks/shadowsocks-android/releases)
## ShadowsocksR（简称SSR）
* [ShadowsocksR（Win）](https://github.com/shadowsocksrr/shadowsocksr-csharp/releases)<br>
* [ShadowsocksR（Mac）](https://github.com/qinyuhang/ShadowsocksX-NG-R/releases)<br>
* [ShadowsocksR（Android）](https://github.com/shadowsocksrr/shadowsocksr-android/releases)<br>
[回到顶部](#readme)
## V2ray（简称V2）
* [V2ray官方使用手册](https://www.v2ray.com/)
* V2ray的Windows端图形界面工具V2RayW和V2RayN
  * [V2RayW](https://github.com/Cenmrev/V2RayW/releases)<br>
  * [V2RayN](https://github.com/2dust/v2rayN/releases)<br>
* V2ray的Mac端图形界面工具V2RayX和V2RayU
  * [V2RayX](https://github.com/Cenmrev/V2RayX/releases)<br>
  * [V2RayU](https://github.com/yanue/V2rayU/releases)<br>
* [V2ray（Android）](https://github.com/2dust/v2rayNG/releases)<br>
[回到顶部](#readme)
## clash
* [clash（Win）简称CFW](https://github.com/Fndroid/clash_for_windows_pkg/releases)[【CFW使用说明书】](https://docs.cfw.lbyczf.com/)<br>
* [clash（Mac）](https://github.com/yichengchen/clashX/releases)<br>
* [clash（Android）](https://github.com/Kr328/ClashForAndroid/releases)<br>
* **ClashR汉化版，支持SSR和V2订阅**[ClashR汉化版](https://sxcool1024.lanzous.com/i9zpaji)<br>
* [CLASHR各平台相关教程](https://docs.nameless13.com/shr)<br>
[回到顶部](#readme)
## Trojan
* [Trojan-Qt5(Win+Mac)图形界面工具](https://github.com/TheWanderingCoel/Trojan-Qt5/releases)
* [Trojan-Qt5（Android）](https://sxcool1024.lanzous.com/ia7vbhg)
* [Trojan的Windows、macOS、Linux三大平台命令行工具](https://github.com/trojan-gfw/trojan/releases)<br>
* 以上Trojan工具的使用教程请查看**帮助中心**里的[Trojan服务客户端设置教程索引](https://portal.shadowsocks.nl/knowledgebase/151/Trojan-%E6%9C%8D%E5%8A%A1%E5%AE%A2%E6%88%B7%E7%AB%AF%E8%AE%BE%E7%BD%AE%E6%95%99%E7%A8%8B%E7%B4%A2%E5%BC%95.html)<br>
[回到顶部](#readme)
## Mellow
Mellow 是一个基于规则的全局透明代理工具，可以运行在 Windows、macOS 和 Linux 上，也可以配置成路由器透明代理或代理网关，支持 SOCKS、HTTP、Shadowsocks、VMess 等多种代理协议。<br>
* Mellow的[Windows、macOS和Linux安装文件下载](https://github.com/mellow-io/mellow/releases)<br>
[回到顶部](#readme)
## Netch
Netch是一个开源游戏加速器。与需要添加规则以用作黑名单代理的SSTap不同，Netch更类似于SocksCap64，后者可以扫描游戏目录以专门获取其进程名称并通过代理服务器转发其网络流量。现在支持Socks5，Shadowsocks，ShadowsocksR，VMess。<br>
同样，Netch避免了由SSTap引起的受限NAT问题。您可以使用NATTypeTester来测试您的NAT类型。当使用SSTap加速某些P2P游戏连接或该开放式NAT类型需要游戏时，您可能会遇到一些不好的情况，例如无法加入游戏。<br>
* [Netch下载](https://github.com/NetchX/Netch/releases)<br>
[回到顶部](#readme)
## Pharos Pro
* [Pharos Pro(Android)](https://github.com/PharosVip/Pharos-Android-Test/releases)<br>
* Pharos Pro(iOS)，登录非大陆AppleID下载。<br>
[回到顶部](#readme)
## shadowrocket
* [ShadowRocket基础教程](http://laob.me/2300/)<br>
* [ShadowRocket分组、规则自动切换节点](https://blog.minirplus.com/14472/)<br>
[回到顶部](#readme)
***

# 五、其它实用资源、工具
* [免费撸谷歌云300$搭建Trojan的全程记录](https://github.com/sxcool1024/googlecloud/blob/master/README.md)
* [著名摄影大师WANIMAL原版作品下载(已分享16.1G共8765张原图，持续更新中)](https://github.com/sxcool1024/WANIMAL-1983/blob/master/README.md)
* [机械工业出版社原版PDF电子书下载，提供当当网一键搜索查询(已分享2542册书籍，持续更新中)](https://github.com/sxcool1024/-Machinery-Industry-Press/blob/master/README.md)
* [《20世纪中华歌坛名人百集珍藏版合集》102张原版CD音轨](https://github.com/sxcool1024/20th-Century-Music)
* [周杰伦无损合集，发烧友正版碟片提取原版音轨](https://github.com/sxcool1024/Jay)
* [Android短信轰炸机](https://sxcool1024.lanzous.com/b00zd45xg)
* [真正的全局代理工具sstap](https://474b.com/file/25713053-442234826)
* [TikTok破解版Android，可注册留言、点赞、私信，支持一键保存无水印视频、保存视频为gif动图，不插卡，不用翻墙](https://474b.com/file/25713053-438607236)
* [91app安装地址，不要通过扫码安装，安装地址复制到手机浏览器打开下载](https://aff.91porn005.me/aff-afeFw)
* [【草榴Android】](https://github.com/yuuwill/1024app-android/releases)  [【草榴官网（需科学上网）】](http://t66y.com/index.php?u=297138&ext=e4669)
* 手机影视神器，摆脱爱奇艺、优酷、腾讯平台的长时间广告骚扰和会员限制：[小小影视永久官网](http://www.wangdunwen.com/?inviteCode=ID3WVM)、[南瓜影视永久官网](https://ng33.app/?channelCode=share?appkey=ayo1id&recommend=20965059)、[冬瓜影视永久官网](https://dg77.app/?channelCode=share?appkey=zphsu3&recommend=4897090)、[卧龙影视官网](https://www.wolong.tv)(邀请码：WL345597)。**这些APP都不需要花钱买会员，会员获取方式就是推荐其他人下载，表内规则请以最新APP为准。手机浏览的可左右滑动下方表格**

| 影视APP | 小小影视 | 卧龙影视 | 南瓜影视 | 冬瓜影视 |
| :----: | :----:  | :----:                   | :---:   | :----:  |
| 影片片头广告 | ✔7s | ✘ | ✔5s可跳过 | 同南瓜 |
| 打开APP广告 | ✔7s可跳过 | ✔5s可跳过 | ✔5s无法跳过 | 同南瓜 |
| 缓存下载 | ✔ | ✘ | ✔ | ✔ |
| 下载 | [小小影视官网](http://www.wangdunwen.com/?inviteCode=ID3WVM) | [卧龙影视官网](https://www.wolong.tv)(邀请码：WL345597) | [南瓜影视永久官网](https://ng33.app/?channelCode=share?appkey=ayo1id&recommend=20965059) | [冬瓜影视永久官网](https://dg77.app/?channelCode=share?appkey=zphsu3&recommend=4897090) |
***
* 洛雪音乐助手桌面版，目前用的最好用的听歌软件，聚合全网音乐资源，90%以上都是无损，可直接下载。[官网](https://github.com/lyswhut/lx-music-desktop/releases)<br>
* 黑鸟视频播放器[官网](https://guihet.com/blackbird-player.html)（自带直播源，持续更新，只有Windows版）<br>
* 百度云盘搜索工具[下载地址](https://sxcool1024.lanzous.com/i9wiekd)，六个搜索引擎，搜索整个百度云库，急速高效，自带提权码。<br>
* iPhone快捷指令分享[【下载YouTube、Twitter视频】](https://twitter.com/sxcool1024/status/1236090141606694912?s=20)[【举牌小人图片生成器】](https://twitter.com/sxcool1024/status/1249974654325813248?s=20)[【文字转二维码】](https://twitter.com/sxcool1024/status/1249974654325813248?s=20)<br>
[回到顶部](#readme)
###### 实用油猴脚本分享，[油猴安装地址](http://www.tampermonkey.net/)
<details>
  <summary>43个油猴脚本下载，点黑三角可查看详情https://474b.com/file/25713053-440658806</summary>
1、	(持续更新)CSDN页面浮窗广告完全过滤净化(净化复制内容_自动展开_让你专注于文章_不影响功能使用).user.js<br>
 <a href="http://www.google.com.hk">2、	4399Clear.user.js</a><br>
3、	AC-baidu_重定向优化百度搜狗谷歌搜索_去广告_favicon_双列.user.js<br>
4、	CSDN Clean.user.js<br>
5、	CSDN,博客园，脚本之家，简书，segmentfault,知乎广告屏蔽.user.js<br>
6、	CSDN、ITeye 彻底去广告，自动展开，去弹窗，免会员，净化剪贴板，防止跳转，上次测试完全可用：20190829.user.js<br>
7、	CSDN免登录+极简化.user.js<br>
8、	CSDN去除二维码图片.user.js<br>
9、	csdn瘦身.user.js<br>
10、	CSDN阅读模式.user.js<br>
11、	Forum Master?Discuz! Revision.user.js<br>
12、	Github 镜像访问，加速下载.user.js<br>
13、	Popup Search.user.js<br>
14、	Userscript+_Show Site All Userjs.user.js<br>
15、	『净网卫士』 吾爱破解论坛.user.js<br>
16、	【懒人工具箱】集成全网VIP视频免费破解去广告、百度网盘直接下载、知乎视频下载、微信公众号文章音频视频图片素材下载、淘宝优惠券便捷查询+高佣返利通道等多合一版.user.js<br>
17、	图像优化.js<br>
18、	培训机构提醒.user.js<br>
19、	工具合集：搜索引擎结果去重，广告过滤  + 网页网盘链接状态自动判断 + 知乎外链免确认 + QQ音乐付费无损音乐免费下载 + 拒绝二维码登录 + Bilibili 视频默认选择最高清晰度 ++.user.js<br>
20、	广告杀手ADkiller.user.js<br>
21、	廖雪峰教程阅读模式.user.js<br>
22、	懒人专用，全网VIP视频免费破解去广告、全网音乐直接下载、百度网盘直接下载、知乎视频下载等多合一版。长期更新，放心使用。.user.js<br>
23、	批改网工具箱, 允许复制粘贴拖拽, 去广告, 美化, etc(有效且最新).user.js<br>
24、	拒绝二维码登录.user.js<br>
25、	改变网页背景为淡灰色.user.js<br>
26、	文件名称.bat
27、	百度文库破解加强助手、 CSDN阅读增强助手、知乎视频下载、抖音去水印原视频下载、全网VIP视频破解，去广告.user.js<br>
28、	百度系网站去广告.user.js<br>
29、	百度网盘资源_搜索引擎_聚合.user.js<br>
30、	知乎免登录.user.js<br>
31、	知乎网页助手，5大功能集于一身.user.js<br>
32、	网址导航去广告.user.js<br>
33、	网盘自动填写密码【威力加强版】.user.js<br>
34、	胡萝卜周验证码.user.js<br>
35、	自动去除CSDN插入图片水印.user.js<br>
36、	自动展开全文.user.js<br>
37、	菜鸟教程去广告，清爽学习.user.js<br>
38、	计时器掌控者_视频广告跳过_视频广告加速器.user.js<br>
39、	购物党自动比价工具-领取淘宝内部券.user.js<br>
40、	超星网课助手(考试专版).user.js<br>
41、	跳过网站等待、验证码及登录(修复版).user.js<br>
42、	迅雷会员，迅雷vip，迅雷白金超会帐号密码.user.js<br>
43、	高级求职助手招聘网站助手，支持前程无忧、智联招聘、BOSS直聘、拉钩网、猎聘网、58同城、百度百聘.user.js<br>
</details>

`关于iOS平台的科学上网工具，目前支持协议较完善的有shadowrocket、suerge、Quantumult、Pharos等，需要用非大陆AppleID下载且收费，请大家自行注册购买，不会的加群找我`

获取提取码请加电报群
# 电报交流群：https://t.me/sxcool1024g
[回到顶部](#readme)



