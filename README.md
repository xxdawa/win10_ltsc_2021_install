# LTSC_2021
Windows 10 Enterprise LTSC 2021 体验

#  1、获取系统镜像文件
简体中文版下载地址：
https://isofiles.bd581e55.workers.dev/Windows%2010/Windows%2010%20Enterprise%20LTSC%202021/19044.1288_Enterprise_2021_LTSC/zh-cn_windows_10_enterprise_ltsc_2021_x64_dvd_033b7312.iso

# 2、创建USB可启动安装盘
推荐使用rufus工具，工具已提供，或者到官网下载，官网地址：https://rufus.ie/zh/

# 3、安装系统
电脑USB接口插上安装U盘，重新启动电脑，到BIOS界面不停按F12（依据电脑品牌型号不同）直到进入启动菜单选项，选择U盘启动，然后根据界面指引开始安装系统

# 4、系统更新
从桌面依次进入开始-设置-更新和安全-检查更新，单击“检查更新”，系统会自动下载安装更新

# 5、系统激活
KMS激活有效期180天，到期前再激活可以一直续期

用命令行kms激活示例：

使用管理员权限打开命令提示符，依次执行以下3条命令

    slmgr /ipk M7XTQ-FN8P6-TTKYV-9D4CC-J462D 

    slmgr /skms kms.03k.org 

    slmgr /ato 

# 6、系统初体验

使用发现的两个问题：
1、wsappx进程占用过高 
2、中文输入法不显示候选框

问题原因与解决方法：

LTSC_2021系统精简掉了VCLibs组件，影响了中文输入法，安装VCLibs库解决。

所需VCLibs安装包已提供，详细下载安装步骤如下：

1、首先下载Microsoft.VCLibs组件。
进入网站 https://store.rg-adguard.net 这个网站可以下载微软应用商店所有应用的离线安装包，第一栏选ProductId，第二栏输入9wzdncrfjbmp，第三栏确保是RP再按勾，接着在下方选择Microsoft.VCLibs.140.00_14.0.30704.0_x64__8wekyb3d8bbwe.appx下载，或者直接使用如下链接下载：http://tlu.dl.delivery.mp.microsoft.com/filestreamingservice/files/1ee8f2d3-cfbe-4514-a83a-5aaadb44df5e?P1=1682217094&P2=404&P3=2&P4=IVamZnjzhIwP%2fSMVVNpTuc8XDSA6K7O3LFJq8MixFJsTDteEqs%2fPTtTWrc4GgQ9y%2bNnw4FqmWPiOiyuBDXpY8A%3d%3d

2、使用powershell命令安装VCLibs组件。
使用管理员权限打开powershell，输入命令
    Add-AppxPackage -Path <此为上一步下载的文件路径>
然后按Enter执行，命令示例：
    Add-AppxPackage -Path C:\Users\你的用户名\桌面\Microsoft.VCLibs.140.00_14.0.30704.0_x64__8wekyb3d8bbwe.appx 
安装完后即可解决上述问题，无需重启，进程占用随即会变成0%，输入法也正常了。
