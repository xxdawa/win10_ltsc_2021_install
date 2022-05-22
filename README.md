# LTSC_2021 试用
Windows 10 Enterprise LTSC 2021 体验

# Windows 10 Enterprise LTSC 2021 镜像文件获取
zh-cn_windows_10_enterprise_ltsc_2021_x64_dvd_033b7312.iso 64位简体中文版下载地址，镜像文件大小4.7G
https://isofiles.bd581e55.workers.dev/Windows%2010/Windows%2010%20Enterprise%20LTSC%202021/19044.1288_Enterprise_2021_LTSC/zh-cn_windows_10_enterprise_ltsc_2021_x64_dvd_033b7312.iso

en-us_windows_10_enterprise_ltsc_2021_x64_dvd_d289cf96.iso 64位英文版下载地址，镜像文件大小4.6G
https://isofiles.bd581e55.workers.dev/Windows%2010/Windows%2010%20Enterprise%20LTSC%202021/19044.1288_Enterprise_2021_LTSC/en-us_windows_10_enterprise_ltsc_2021_x64_dvd_d289cf96.iso

# 使用下载的镜像文件，创建USB可启动安装盘
推荐使用rufus工具，rufus-3.18下载地址

https://objects.githubusercontent.com/github-production-release-asset-2e65be/2810292/6857babf-ea76-483c-bde8-9e000153abeb?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIWNJYAX4CSVEH53A%2F20220521%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20220521T231658Z&X-Amz-Expires=300&X-Amz-Signature=7b128a93ea6fc814d67ca0d81458fa464e2333572a183fd87d8b679428f717c1&X-Amz-SignedHeaders=host&actor_id=0&key_id=0&repo_id=2810292&response-content-disposition=attachment%3B%20filename%3Drufus-3.18.exe&response-content-type=application%2Foctet-stream

# 安装系统
插上创建好的启动安装U盘，重新启动电脑，在BIOS界面按F12（依据电脑品牌型号不同）选择U盘启动，开始安装

# 系统更新
从桌面依次进入开始-设置-更新和安全-检查更新，单击“检查更新”，系统会自动下载安装更新

# 系统激活
KMS激活有效期180天，到期前再激活可以一直续期

用命令激活示例：
使用管理员权限打开命令提示符，依次执行以下3条命令

slmgr /ipk M7XTQ-FN8P6-TTKYV-9D4CC-J462D   --安装密钥

slmgr /skms kms.03k.org  --设置KMS服务器

slmgr /ato  --激活

# 开始使用
初次使用，打字时发现输入法异常，没有候选词
