# btpanel-v7.7.0 + 破解脚本
## [btpanel-v7.7.0-backup  官方原版v7.7.0版本面板备份](https://github.com/zhucaidan/btpanel-v7.7.0)

**Centos/Ubuntu/Debian安装命令 独立运行环境（py3.7）：**

```Bash
curl -sSO https://raw.githubusercontent.com/zhucaidan/btpanel-v7.7.0/main/install/install_panel.sh && bash install_panel.shbsp;
```

**如果遇到重启后宝塔乱码 请DD最新版Debian系统然后修改语言区域：**


```Bash
nano /etc/default/locale
```

```Bash
LANG=en_US.UTF-8
```

修改后保存文件，重启VPS即可。



## [宝塔脚本](https://github.com/ztkink/bthappy)

[宝塔Linux面板最新7.7专业版破解方式 | 柴郡猫 (cheshirex.com)](https://www.cheshirex.com/6288.html)

**2022年5月25日更新：**

发一下别人备份的7.7版本以及一键破解脚本。

新装面板，按照顺序依次安装7.7原版，执行一键破解脚本，然后执行一键优化脚本即可。

**提示：**破解有风险，请勿在正式环境中使用。本博客仅做收集备份。

下列资源本站2022年5月25日备份：[OneDrive](https://cheshirex-my.sharepoint.com/:f:/g/personal/cheshirex-down_cheshirex_onmicrosoft_com/EsjC5nEj3wVOuxJwCWouRBABQKPqZdNrdw6oWvojBsZfLg?e=s7v7FT)

 

宝塔面板7.7原版

```
curl -sSO https://raw.githubusercontent.com/LeeSpo/btpanel-mix/main/install/install_panel.sh && bash install_panel.sh
```

一键破解脚本

```
curl -sSO https://raw.githubusercontent.com/ztkink/bthappy/main/one_key_happy.sh && bash one_key_happy.sh
```

破解脚本备用地址

```
curl -sSO https://cdn.cheshirex.com/uploads/sh/one_key_happy.sh && bash one_key_happy.sh
```

一键优化脚本

```
wget -O optimize.sh https://f.cccyun.cc/bt/optimize.sh && bash optimize.sh
```

本文目录



- \1. 更新说明
  - [1.1. 优化脚本](https://www.cheshirex.com/6288.html#toc_id_1_1)
  - [1.2. 7.7原版第三方存档](https://www.cheshirex.com/6288.html#toc_id_1_2)
  - [1.3. 7.7原版一键开心脚本](https://www.cheshirex.com/6288.html#toc_id_1_3)
- [2. 特别提醒](https://www.cheshirex.com/6288.html#toc_id_2)

### 更新说明

#### 优化脚本

```
一键修改宝塔面板模板、去除强制登陆、一键修复面板、一键更换yum源、清除系统垃圾缓存、系统优化等
https://gitee.com/gacjie/btpanel_tools
wget -O btpanel_tools.sh https://download.btpanel.cm/tools/btpanel_tools.sh && bash btpanel_tools.sh

#宝塔面板一键优化补丁 -彩虹
1.去除宝塔面板强制绑定账号
2.去除各种删除操作时的计算题与延时等待
3.去除创建网站自动创建的垃圾文件（index.html、404.html、.htaccess）
4.关闭未绑定域名提示页面，防止有人访问未绑定域名直接看出来是用的宝塔面板
5.关闭活动推荐与在线客服
6.去除自动校验文件与上报信息定时任务
7.去除面板日志与网站绑定域名上报
适用7.7版本：wget -O optimize.sh https://f.cccyun.cc/bt/optimize.sh && bash optimize.sh
适用7.9版本：wget -O optimize.sh https://f.cccyun.cc/bt/optimize_new.sh && bash optimize.sh
```

#### 7.7原版第三方存档

```
纯原版1：curl -sSO https://raw.githubusercontent.com/zhucaidan/btpanel-v7.7.0/main/install/install_panel.sh && bash install_panel.sh
纯原版2：wget -O install.sh https://f.cccyun.cc/bt/install_6.0.sh && bash install.sh
升级(降级)到7.7命令： curl http://f.cccyun.cc/bt/update6.sh|bash
```

#### 7.7原版一键开心脚本

```
curl -sSO https://raw.githubusercontent.com/ztkink/bthappy/main/one_key_happy.sh && bash one_key_happy.sh
```

<!--手动解锁宝塔所有付费插件为永不过期-->
文件路径：www/server/panel/data/plugin.json
搜索字符串："endtime": -1 全部替换为 “endtime": 999999999999
<!--手动阻止解锁插件后自动修复为免费版-->
chattr +i /www/server/panel/data/plugin.json

**2022年2月28日更新：**

很多同学还是想用破解版，下面文章是7.7版本，最新版已经修复了破解漏洞。

想用破解版可以考虑下这个，本人没有使用。重要业务不建议使用破解版。
https://www.hostcli.com/
宝塔纯净版 7.6.0版本。
剥离了所有与宝塔官方的通信、上报、下发；并且不与本站纯净版服务器通信；
提升为企业会员，免费使用软件商店中的所有[企业版插件]、[专业版插件]、[运行环境]、[免费插件]、[宝塔插件]；

 

**2021年12月20日更新：**

//禁止解锁插件后自动修复为免费版
文件路径：www/server/panel/data/repair.json
查找字符串："id": 16，将这段修复权限的代码删除

//禁止宝塔面板检测升级，防止失效
文件路径：www/server/panel/data/plugin.json
查找字符串：name": “coll_admin"，将这段里的update_mgs删除或者改为null

**2021年12月2日更新：**

有可能在你修改代码安装程序后发现又是未授权。这种情况就再改一次，等修改完成，并且安装好付费插件后开启面板的离线模式。

不开离线模式宝塔下次打开还会自动读取云端列表，给你恢复未授权。

------

2021年11月29日测试破解正常，付费插件可以正常使用。

安装宝塔面板后进入文件管理

找到www/server/panel/data/plugin.json文件并编辑

提醒：修改前，可以先备份一次该文件。

搜索

```
"endtime": -1
```

会找到很多结果，全部替换为

```
"endtime": 999999999999
```

![img](https://www.cheshirex.com/wp-content/uploads/2021/11/QQ%E6%88%AA%E5%9B%BE20211129185922.png)

因为搜索出来的结果比较多，我们可以使用宝塔面板的批量替换功能全部替换掉。看上图操作即可。

![img](https://www.cheshirex.com/wp-content/uploads/2021/11/QQ%E6%88%AA%E5%9B%BE20211129190032.png)

 

此时我们只是付费插件免费了，但是面板首页还是显示的免费版。

可以通过下面的方式来解决。

还是在上面的文件内：

搜索：\u63a8\u8350

在结果前有"panel_pro": -1, “panel_ltd": -1,的代码。我们将-1改为0即可。

-1代表没有授权，0代表专业版永久授权。

![img](https://www.cheshirex.com/wp-content/uploads/2021/11/QQ%E6%88%AA%E5%9B%BE20211129190624.png)

替换后就会显示永久授权了。

![img](https://www.cheshirex.com/wp-content/uploads/2021/11/QQ%E6%88%AA%E5%9B%BE20211129190820-1030x521.png)

## 特别提醒

建议修改并且安装过我们需要的插件后，开启面板的离线模式。否则宝塔面板后期自动升级可能会将修改的内容覆盖掉。

本人确认宝塔会自动升级！并且从官方证实了此信息。

![img](https://www.cheshirex.com/wp-content/uploads/2021/11/QQ%E6%88%AA%E5%9B%BE20211129190852-1030x449.png)

**Posted by [柴郡猫](https://www.cheshirex.com/author/cheshirex)
