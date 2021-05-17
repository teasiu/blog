---
layout: title
title: slitaz
date: 2021-05-17 10:31:53
tags:
top: 10
---

# 神雕定制slitaz中文版
  Slitaz 是一个免费小巧的GNU/Linux发行版。它可以从光盘或USB设备加载，完整地在内存中运行，也可以安装到硬盘中。
  Slitaz以LiveCD的形式 发布，您可以把它刻录到光盘，并从光盘启动。你也可以将它与其它例如win-pe🈴盘。
  LiveCD提供一个特色十足的、图形界面的发行 版，可以保存您的数据和个人设置到其他设备中。
  这个系统可以通过Tazpkg软件包管理器添加软件来增加各种各样的功能，也可以用它升级系统来保持系统最 安全、最新.
# 支持自主定制
制作了新型定制办法，定制方法已经在源码中说明，请参照自主定制属于你的slitaz。
本定制手法需要在ubuntu20.04下操作：
首先需要配置ubuntu的docker和必要的环境：
```
sudo apt update && sudo apt install p7zip-full genisoimage curl git bash
一键安装docker
curl -fsSL https://get.docker.com | bash -s docker --mirror Aliyun
```
<!-- more -->
然后
```
git clone https://github.com/teasiu/slitaz5cn.git
cd slitaz5cn
sudo bash mk-slitaz64.sh
```
完成后将会自动在文件夹内多了一个定制好的slitaz5.0-rolling-core64-cn.iso
修改和添加软件包，请进入packages的gen-slitaz64.sh编辑和调整。
# 使用
请仔细阅读下面这段定制说明。

1. 根据官方每周固件进行中文定制。最新版本silitaz5.0-rolling-core64-chinese.iso
如果你的电脑内存超过4G，请使用64位。低于4G，请使用32位(32位无法识别超过4G的内存)。
2. 管理账号root密码root,用户账号tux密码为tux
3. 启动和安装
支持各种引导开机,grub4dos，grub2，syslinux，支持efi启动。
可以安装到U盘随身启动，也可以和其他pe合盘。
可以安装到硬盘也可以网络pxe启动。
启动代码请自行在你的启动菜单添加使用:
【  root=/dev/null video=-32 lang=zh_CN kmap=us tz=Asia/Shanghai autologin 】
4. 内置中文输入法,支持拼音,五笔等,ctrl+空格切换开关,shift切换中英文输入。
5. 内置神雕的国内软件源地址,自动从国内源下载和更新软件包。
6. 国内源镜像http://ecoo.top:8083/dl/slitaz/iso/rolling
7. 增加sudo加权功能,在命令前sudo即可使用管理权限。
8. 增加著名的诺顿精灵GHOST。可用于系统备份维护。
9. 内置gpartd磁盘分区格式程序,可用于电脑硬件维护。
10. 内置tazpanel,可查看系统硬件环境,软件环境,启动参数等。
11. 内置5000多个软件安装包的在线安装程序,可以自由安装。
12. 已添加虚拟机桌面驱动,可以在虚拟机中显示桌面。
13. 已添加ssh启动,可远程ssh登陆。(dropbear)
远程登录账号tux密码tux，登陆后sudo可提权。
14. 已添加gftp软件。另外,自带的busybox的ftpput和ftpget命令也集成。
15. 集成了transmission BT远程下载并安装最新web-ctrl,远程登陆账号tux密码tux。
16. 集成vlmcsd最新版的KMS服务器,远程激活windows。
17. 集成一键开启samba3.6版网络文件共享服务
支持在文件管理器输入smb://192.168.1.1访问网络共享
支持挂载openwrt和synology群晖网络存储空间，
sudo mount.cifs //192.168.1.1/usb /mnt/ -o vers=2.0
sudo mount.cifs -o username=admin,password=passwd,
rw,forceuid=nobody,forcegid=nogroup,dir_mode=0777,file_mode=0777,vers=2.0
//192.168.111.2/volume1/files /mnt
18. 内置fbinst软件,可使用命令行各种骚操作。
19. 编译定制了专用火狐浏览器中文版，支持online自动安装。
修复输入法在火狐浏览器下的使用。
20. 修复了解压缩软件并添加了中文。修复 rar && unrar
21. 内置git-server服务器，让你随时随地白嫖免费的高速上传下载空间。
作为一个系统玩家，这个特别实用哦。
详见内置文档<a href="#git">白嫖5GB仓库指南使用教程</a>。
22. 添加了安装到硬盘的脚本，支持一键安装slitaz系统到本地硬盘。
安装到硬盘后，请将/etc/init.d/system.sh最后某行
echo "tux:tux" | chpasswd删除。便以你修改登录密码生效。
23. 添加了axel多线程下载软件，直接在终端  （axel n 10 下载地址）就是10线程下载。
24. 添加rsync备份神器。
25. 添加了很多的小工具，在我的文档文件夹内。 
项目下载地址更新为(三处同步更新):
https://github.com/teasiu/slitaz5cn
https://sourceforge.net/projects/slitaz/
http://www.slitaz.cn:8083 （推荐）



