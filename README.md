# LTSC_2021
Windows 10 Enterprise LTSC 2021 体验

#  1、获取系统镜像文件
简体中文版下载地址：
https://isofiles.bd581e55.workers.dev/Windows%2010/Windows%2010%20Enterprise%20LTSC%202021/19044.1288_Enterprise_2021_LTSC/zh-cn_windows_10_enterprise_ltsc_2021_x64_dvd_033b7312.iso

英文版下载地址：
https://isofiles.bd581e55.workers.dev/Windows%2010/Windows%2010%20Enterprise%20LTSC%202021/19044.1288_Enterprise_2021_LTSC/en-us_windows_10_enterprise_ltsc_2021_x64_dvd_d289cf96.iso

# 2、创建USB可启动安装盘
推荐使用rufus工具，rufus-3.18下载地址

https://objects.githubusercontent.com/github-production-release-asset-2e65be/2810292/6857babf-ea76-483c-bde8-9e000153abeb?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIWNJYAX4CSVEH53A%2F20220521%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20220521T231658Z&X-Amz-Expires=300&X-Amz-Signature=7b128a93ea6fc814d67ca0d81458fa464e2333572a183fd87d8b679428f717c1&X-Amz-SignedHeaders=host&actor_id=0&key_id=0&repo_id=2810292&response-content-disposition=attachment%3B%20filename%3Drufus-3.18.exe&response-content-type=application%2Foctet-stream

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
## 1、wsappx进程占用过高 
## 2、中文输入法不显示候选框

问题原因与解决方法：
LTSC_2021系统精简掉了VCLibs组件，影响了中文输入法，安装VCLibs库解决。

## 1、首先下载Microsoft.VCLibs组件。进入网站https://store.rg-adguard.net（这个网站可以下载微软应用商店所有应用的离线安装包），第一栏选ProductId，第二栏输入9wzdncrfjbmp，第三栏确保是RP再按勾下载并记住下载文件位置。

## 2、电脑打开powershell安装VCLibs组件。在powershell中输入命令Add-AppxPackage -Path <此为上一步下载的文件路径> 然后按Enter执行，命令示例：Add-AppxPackage -Path C:\Users\你的用户名\桌面\Microsoft.VCLibs.140.00_14.0.30704.0_x64__8wekyb3d8bbwe.appx 安装完后即可解决上述问题，无需重启，进程占用随即会变成0%，输入法也正常了。
