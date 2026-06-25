> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.coolapk.com](https://www.coolapk.com/feed/63460953?s=Yzg5YzI5YjA2N2EwMmc2OWE5MGUwNnoa1603)

![](http://image.coolapk.com/feed_cover/2025/0319/17/20443820_6345c715_7618_8414_991@1079x485.jpeg)

如何优雅的去除广告和反诈

![](http://avatar.coolapk.com/data/020/44/38/20_avatar_middle.jpg?t=1732176221)

尘尘 pazz

2025-03-19 真我 GT Neo3

[#Magisk 模块#](https://www.coolapk.com/t/Magisk%E6%A8%A1%E5%9D%97?type=12) [#那些好用的 magisk 模块#](https://www.coolapk.com/t/%E9%82%A3%E4%BA%9B%E5%A5%BD%E7%94%A8%E7%9A%84magisk%E6%A8%A1%E5%9D%97?type=12) [#ColorOS15#](https://www.coolapk.com/t/ColorOS15?type=12)  
★1. 前言：  
相信大家都被许多软件的弹窗广告所烦恼，还有小伙伴也有去除手机内置反诈的需求。目前主流的方法就是 hosts 模块或者设置私人 dns。这两种方法都挺好，但也有缺点：  
hosts 可能面临着规则太多导致处理时间长，误杀，耗电；私人 dns 也可能存在安全问题和链接质量问题，如果本地网络较差或者校园网环境，私人 dns 可能延迟较高，打开网页较慢。AdGuardHome 虽然可以设置上游 dns 和配置规则解决，但有这特殊上网需求的小伙伴可能因为不会配置导致使用 AdGuardHome 后代理软件 / 模块使用不了的情况，而且 AdGuardHome 较难去除系统内置反诈。那么有没有一种有效的，通用的，优雅的方法实现 dns 配置，去广告，代理，去除系统反诈的方法呢？有的兄弟，有的![](http://static.coolapk.com/emoticons/v9/coolapk_emotion_13_huaixiao.png)  
---------------------------------------------------  
★2. 实现方法：  
使用 Mihomo 内核的透明代理模块，本教程只讲解如何去除广告等方法，不讲解违规操作，希望审核小编多抬贵手，感谢感谢![](http://static.coolapk.com/emoticons/v9/coolapk_emotion_64_shounuehuaji.png)  
Mihomo 虚空终端官方文档和简介：[查看链接](https://wiki.metacubex.one/ "https://wiki.metacubex.one/")

![](https://image.coolapk.com/feed/2025/0319/17/20443820_db128d0b_7620_3499_894@1080x1910.jpeg.m.jpg)

安装透明代理模块如 box4，akashaProxy 等，我使用的是另外一位作者项目：“C 略 MIX”，不管项目如何，最终到我们手里一般只需要配置模块路径下的 config.yaml 文件。

![](https://image.coolapk.com/feed/2025/0319/17/20443820_b2d04e8d_7620_3507_878@1080x1296.jpeg.m.jpg)

---------------------------------------------------  
★3. 具体配置：  
★3.1 dns 配置  
大多数情况下模块里面都有此配置文件，dns 规则已经是配置好的，我们不需要修改。  
可以按图片里面配置：

![](https://image.coolapk.com/feed/2025/0319/17/20443820_9bd7debe_7620_3515_295@1080x2127.jpeg.m.jpg)

userDirect 和 userProxy 是自定义用户策略组。userProxy 一般情况下不用配置，userDirect 则可以添加内网 ip 规则，防止内网网站无法访问，如你的路由器后台等。这两者在 rule-providers 下定义，他们的配置文件路径如下：

![](https://image.coolapk.com/feed/2025/0319/17/20443820_bfd51c5f_7620_3526_524@1080x1503.jpeg.m.jpg)

这样 dns 解析服务就完成了。  
---------------------------------------------------  
★3.2 去广告配置：  
config.yaml 一般内置了 “秋风广告规则”，如果不再配置的话基本可以去除 80% 左右的广告了。

![](https://image.coolapk.com/feed/2025/0319/17/20443820_5fef2bdc_7620_3535_73@1080x1257.jpeg.m.jpg)

但是有小伙伴可能需要更强力去广告配置，那么如何实现呢？  
★3.2.1 geodata 规则去除  
我们把 config.yaml 文件内容拉到最下面，在 rules 模块中，把我圈住的注释给去掉即可。

![](https://image.coolapk.com/feed/2025/0319/17/20443820_e7295ec3_7620_3543_223@1080x1548.jpeg.m.jpg)

★3.2.2 自定义策略组  
自定义策略组去广告是用 DOMAIN 匹配广告域名利用 Mihomo 的 REJECT 预置出站拦截广告域名。  
首先，在 rule-providers 模块里添加如图所示的策略组，我命名为 adhosts，文件路径为：  
./rule_providers/adhosts.yaml，因此我们需要在这个 adhosts.yaml 文件里添加广告域名，广告域名可以从 10007 大佬的 hosts 规则获取，文件内容写法如下：

![](https://image.coolapk.com/feed/2025/0319/17/20443820_0dc09c8b_7620_3553_298@1080x1326.jpeg.m.jpg)

我把大佬的 3w 规则全添加了![](http://static.coolapk.com/emoticons/v9/coolapk_emotion_64_shounuehuaji.png)。文件写好后打开 config.yaml 文件，滑到最下面的 rules 模块中添加如图所示内容，意思是 adhosts 策略组的 adhosts.yaml 文件中的所有域名被拒绝访问。

![](https://image.coolapk.com/feed/2025/0319/17/20443820_4d5ce3a7_7620_3562_181@1080x1636.jpeg.m.jpg)

这种方法可以随时添加规则而无需重启。  
★3.3 去除反诈：  
需要去除的有：反诈域名，反诈 ip，和系统组件内置反诈。实现原理和 3.2.2 所讲的自定义用户策略组一样，用到 DOMAIN 匹配域名，IP-CIDR 匹配 ip，PROCESS-NAME 匹配系统内置反诈组件的包名。  
首先还和 3.2.2 一样，在 rule-providers 模块里添加如图所示的策略组，命名为 userReject，配置文件路径为：./rule_providers/userReject.yaml，如图所示：

![](https://image.coolapk.com/feed/2025/0319/17/20443820_e7c08887_7620_3572_72@1080x2280.jpeg.m.jpg)

userReject.yaml 配置写法如图所示：

![](https://image.coolapk.com/feed/2025/0319/17/20443820_20242e52_7624_3003_263@1080x2300.jpeg.m.jpg)

图中以 color os 为例，即可屏蔽系统内置反诈和反诈 ip，域名使用 DOMAIN 匹配（图中并没有实例，可参考前面图中写法）。反诈 ip 和域名已经组件包名从阿灵大佬的最新去广告模块获取，我这边只提供一个折腾方法，不想折腾的话可以直接使用阿灵大佬的模块，全部可以去除。  
小米，vivo 系列内置组件包名可从阿灵大佬模块中获取，如图所示：

![](https://image.coolapk.com/feed/2025/0319/17/20443820_30cac043_7624_3007_755@1080x672.jpeg.m.jpg)

此文件里面有各厂商内置反诈的包名。  
此外，Mihomo 还支持配置 hosts，也可以使用 hosts 来去除。在 config.yaml 文件中添加如下内容：

![](https://image.coolapk.com/feed/2025/0319/17/20443820_daf812c9_7624_3011_290@1079x2278.jpeg.m.jpg)

即可去除。Mihomo 的 hosts 规则支持通配符，详细写法可参考官方文档：[查看链接](https://wiki.metacubex.one/config/dns/hosts/?h=hosts "https://wiki.metacubex.one/config/dns/hosts/?h=hosts")  
---------------------------------------------------  
★4. 总结：  
本文只是提供了一种折腾去广告的方法，我也是最近几天看官方文档问 ai 才了解一些，本文可能有出错的地方，欢迎大家指正。  
此外，其他有关代理方面配置问题本文不做涉及，相关教程自行查找。