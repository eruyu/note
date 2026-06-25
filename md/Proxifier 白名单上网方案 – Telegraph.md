> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [telegra.ph](https://telegra.ph/Proxifier-%E7%99%BD%E5%90%8D%E5%8D%95%E4%B8%8A%E7%BD%91%E6%96%B9%E6%A1%88-09-24)

> 方案介绍 此方案的主要特点是：设置电脑只允许咱们指定的软件上网，其它软件未经允许均无法上网（适用于绝大多数的软件），使用此方案不会对用户的电脑产生任何额外的不便，也不会改变用户使用电脑的习惯，只是用户的电脑多了一层强有力的安全保障。

[信息安全技术频道🔎](https://t.me/tg_InternetSecurity)

### 方案介绍

此方案的主要特点是：设置电脑只允许咱们指定的软件上网，其它软件未经允许均无法上网（适用于绝大多数的软件），使用此方案不会对用户的电脑产生任何额外的不便，也不会改变用户使用电脑的习惯，只是用户的电脑多了一层强有力的安全保障。

### 主要功能

> ●只允许指定的软件连接互联网，未指定的软件禁止连接互联网。

> ●可限制软件只能通过代理访问互联网，未通过代理的软件禁止访问互联网。

> ●允许系统自动连网更新或阻止系统自动连网更新。

注：此方案不能替代杀毒软件、不能替代系统更新。

### 程序安装步骤

下载 Proxifier 安装版，不要使用绿色版，请断网安装，在安装前先设置禁止访问 Proxifier 官方网站，使用管理员权限打开 cmd，并输入

echo 127.0.0.1 www.proxifier.com >> C:\Windows\System32\drivers\etc\hosts

见下图：

![](https://telegra.ph/file/1b1b9c79bdeebe9c79e37.png)

下面是软件安装步骤，使用管理员权限运行软件，见下图：

![](https://telegra.ph/file/7f010460200080731ee59.png)

![](https://telegra.ph/file/d6f7933fa45d9cf69d648.png)

![](https://telegra.ph/file/6bee4dcc47a56a2d2ee9c.png)

![](https://telegra.ph/file/d847e938f7cfbf757a89d.png)

![](https://telegra.ph/file/fa768ee1e16374d94d3ea.png)

![](https://telegra.ph/file/57c45dad7405494f5fbb7.png)

![](https://telegra.ph/file/a5384482e6d9f0aae282a.png)

![](https://telegra.ph/file/802754c605ebec99de937.png)

![](https://telegra.ph/file/d02e5fafb4a44ab02fc15.png)

下面请根据自己的实际情况选择一个方案，双击后，在程序的左上角会显示结果，见下图：

![](https://telegra.ph/file/01ae79a4577483145c264.png)

以上为 Proxifier 程序的安装步骤，但还需要设置程序开机器自动启动，这里使用计划任务来实现，请按下面的步骤操作：

在桌面空白的地方点右键，然后点新建，再点快捷方式，输入 taskschd.msc 点下一步，然后使用管理员权限点击桌面的 taskschd 图标，见下图：

![](https://telegra.ph/file/fdcfa852d83fae701087f.png)

点创建任务，然后按下面的步骤操作：

![](https://telegra.ph/file/adbfc9d06ac0315a45e3d.png)

![](https://telegra.ph/file/84cc031d543bb7446380e.png)

![](https://telegra.ph/file/1c8ca44603e90e6b674ad.png)

![](https://telegra.ph/file/3d1c5198e7d50afb3e09f.png)

![](https://telegra.ph/file/a9305fcbae46375f68e0a.png)

![](https://telegra.ph/file/691f75ad66231d2df3adb.png)

经过以上步骤，计划任务已经设置好了，但还需要做一下验证，确保设置成功。

### 验证计划任务

重新启动电脑，然后在屏幕中间的最下面点右键，点启动任务管理器，再点显示所有用户的進程，如果看到 Proxifier.exe 程序，则表示设置成功。

![](https://telegra.ph/file/0cb1f949a40f1e08a2ce7.png)

经过验证，此方案算完成了。

### 添加程序连接网络（一般情况下不需要操作，有需要才操作）

首先拔掉网线，然后打开任务管理器，找到 Proxifier.exe ，点右键，再点结束進程，再到桌面打开 Proxifier 程序，见下图：

![](https://telegra.ph/file/9f250313ecae2dfa4f852.png)

下面以添加 Potplayer 播放器通过破网软件连接网络为例：

![](https://telegra.ph/file/610c6e907fbaaacf69961.png)

这是一般的情况，有个别软件需要添加两个程序才能连接网络，例如 smplayer 播放器，则需要添加 smplayer.exe 与 mpv.exe 才能翻墙，这是特殊情况，一般只需要添加一个程序即可。

### 相关问答

1、此方案与频道发布的网络安全一键设置效果一样吗？

答：网络安全一键设置方案是对已知的程序做防御，对未知的程序或木马不起作用,《Proxifier 白名单上网方案》能够对未知的应用程序或木马起到防御作用。

2、目前频道推出的哪个方案防御能力最好？

答：没有最好的防御方案，但是目前已知的防御能力最强的防御方案是《系统半隔离安全上网方案》+ 《Proxifier 白名单上网方案》的组合，曾经有人测试过，在安装了《系统半隔离安全上网方案》+ 《Proxifier 白名单上网方案》的电脑上安装了一个 QQ 大木马，结果 QQ 大木马被堵在系统里出不来了，由此可见其防御能力之强。

3、《Proxifier 白名单上网方案》可以杀毒吗？

答：《Proxifier 白名单上网方案》不是杀毒软件，但《Proxifier 白名单上网方案》可以防御病毒泄漏系统隐私，能够起到杀毒软件起不到的作用，举个例子：前面有一道门，杀毒软件就好像是一个门卫，当有小偷要進来的时候，杀毒软件会阻止小偷進来，但是如果小偷乔装打扮一下，杀毒软件就无法识别了，此时小偷便可進到门里去，如果你的门里面没有其它的防御机制，小偷就会偷东西出去，如果你设置了《Proxifier 白名单上网方案》，那么小偷即使進去了，也无法偷东西出去。

4、《Proxifier 白名单上网方案》与《系统半隔离安全上网方案》有什么关系？

答：《Proxifier 白名单上网方案》侧重点在于防止电脑病毒泄漏系统隐私，在防御病毒方面要强于《系统半隔离安全上网方案》，但是《Proxifier 白名单上网方案》对防止 Windows12 泄漏用户隐私也能起到一定的作用。而《系统半隔离安全上网方案》的侧重点在于防止 Windows 系统泄漏隐私，在防御 Windows 系统泄漏隐私方面强于《Proxifier 白名单上网方案》，但《系统半隔离安全上网方案》又能防御病毒泄漏系统隐私。

5、此方案适用于哪些系统？

答：此方案在 Win7、Win8.1、Win10 系统上都适用。

6、此方案能否防御手写板病毒或 U 盘病毒？

答：可以防御，如果对系统安全这一块非常注重的朋友，建议系统半隔离安全方案与此方案一起使用，防御效果极佳。

7、Win10 系统使用此方案有什么需要注意的事项吗？

答：Win10 系统使用此方案，必须先使用频道发布的《系统与网络安全一键设置工具》后方可使用。