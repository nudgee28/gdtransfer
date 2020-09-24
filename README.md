# gdtransfer
百度 115 转存 谷歌网盘GD 方法介绍

希望GD的资源越来越丰富！！！

**必要工具**

1.GCP 谷歌云一台
2.谷歌网盘账号，带团队盘（G-suit账号最好）


------------


> 第一步：
创建GCP服务器

地域：香港最好，其他没试过，

配置：2 个 vCPU，8 GB 内存

硬盘：选择SSD 大小至少70 建议100g以上（好像是限制到250g）看需求了

系统：debian-10 吧

*其他基础设置和搭建翻墙服务器一样


------------


> 第二步：
安装DD系统

```javascript
wget --no-check-certificate -qO InstallNET.sh 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh' && bash InstallNET.sh --ip-addr 10.170.0.20 --ip-mask 255.255.255.0 --ip-gate 10.170.0.1 -dd 'https://api.moeclub.org/GoogleDrive/1C9Y0Iu1pGX4-blb_3G49jOqv13Zeka6-'
```
    --ip-addr X.X.X.X  （10.170.0.20）      #更换成服务器内部ip (记住是内部ip不是你的外网ip)
    --ip-gate X.X.X.1  （10.170.0.1）   #把X.X.X.X更换成X.X.X.1   (如果服务器内部ip为10.0.170.18需要更换成10.170.0.1)

 *windows镜像精简版文件地址登录用户名及密码windows镜像精简版文件地址登录用户名及密码*
 

    ** 可以替换上面的地址看你喜欢装那个了**
	#DD Windows7 64位 旗舰精简版 [账户Administrator密码www.nat.ee]
    https://api.moeclub.org/GoogleDrive/1C9Y0Iu1pGX4-blb_3G49jOqv13Zeka6-
    
    #DD Windows10 64位 企业精简版 2019LTSC [账户Administrator密码www.nat.ee]
    https://api.moeclub.org/GoogleDrive/1pUNKV0nQvFXDZYJnfq2FzEfQNCZ3_5g7
	
	
#### Tips：

- 装机至少20分钟，中间会失联，不要着急耐心等待：）
- 用WINDOWS 自带的远程桌面链接，MAC系统用 MICORSOFT REMOTE DESKTOP BETA
- 强调下远程桌面最好一定要用梯子连，不然卡的厉害，不挂梯子，不要觉得机器卡，其实是你网络卡（如果你有国内大云厂的机子，那是最好连起来好流畅！）
- 装完如果发现上不了网，请确认网络设置里面DNS有没有添加，没有的话，打上8.8.8.8/8.8.4.4`


------------




> 第三步：
安装软件挂载Google Driver


##### 1.Raidrive（推荐）
下载地址：https://www.raidrive.com/
推荐理由：免费傻瓜型操作



##### 2.Google Drive File Stream
下载地址: https://support.google.com/a/answer/7491144?hl=zh-Hans

必须要是Gsuit账号，优点是 如果你下载到本地服务器之后再移动到挂载盘速度能有200m/s
缺点盘被默认成FAT32大小和你系统盘一样大


##### 3.RcloneBrowser
下载地址: https://github.com/mmozeiko/RcloneBrowser
reclone感觉设置麻烦了点 没第一个方便


------------


> 第四步：
安装百度网盘，115，6盘

下载目录设置成挂载的网盘目录


------------




##写在最后：

**1.费用怎么算的**
谷歌云只计算出站流量，GCP到google driver的上传流量是免费的，
所以你只需要付机器的费用，和在下载过程中很小一部分流到站外的流量，几乎可以忽略不计。

**2.如何节省费用**
如果没有下载任务请关机，直接远程在系统关机，gcp服务器也会自动关机。

**3.还有什么小技巧**
下载谷歌云app，这样你能在app里面关闭和开启实例，而不需要登入网页操作。



------------



##总结:
现在最大的瓶颈是你百度网盘和115 这些下载工具下载的速度，百度就不去吐槽了好慢，10m/s左右
注意：下载文件是先要缓存到本地再上传的，
所以如果下载超大的单个文件那么盘得大一点不然后面只能删盘重建服务器。#下载完一个文件就上传的，理论上来说，只要你同时下载的文件不超过自带硬盘的大小，你可以无限上传！不用什么1t啥的大盘鸡，没意义。
