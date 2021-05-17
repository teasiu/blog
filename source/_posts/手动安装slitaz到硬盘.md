---
title: 手动安装slitaz到硬盘
date: 2021-05-17 12:34:02
tags:
---

## 手动安装slitaz到硬盘
Manual ('By Hand') Installation
# 1.首先准备好你将要安装slitaz的目标硬盘分区
需要ext4格式化这个分区，假如是sda1（以下以sda为例，不同的情形请自行修改）
```
mkfs.ext4 /dev/sda1
```
# 2.挂载
```
mkdir /mnt/target
mount /dev/sda1 /mnt/target
```
# 3.准备下载一个iso格式的镜像文档
<!-- more -->
中文版永久下载地址（每周更新）
https://github.com/teasiu/slitaz5cn/releases/latest
取出iso里面的内核文件bzImage和系统文件rootfs.gz，并拷贝到挂载的目标硬盘分区
```
mount -o loop slitaz.iso /media/cdrom
mkdir /mnt/target/boot
cp -a /media/cdrom/boot/vmlinuz-* /mnt/target/boot
cp -a /media/cdrom/boot/rootfs.gz /mnt/target  
```
如果你直接下载内核文件bzImage和系统文件rootfs.gz，则直接
```
mkdir /mnt/target/boot
cp -a bzImage /mnt/target/boot
cp -a rootfs.gz /mnt/target 
```
# 4.解压系统文档
```
cd /mnt/target
unlzma < rootfs.gz | cpio -id
rm rootfs.gz init
```
# 5.安装grub启动到目标磁盘
```
grub-install --root-directory=/mnt/target /dev/sda 
```
添加启动菜单
```
leafpad /mnt/target/boot/grub/menu.lst
```
例如这个样子：
```
title SliTaz GNU/Linux 5.0
   root(hd0,0)
   kernel /boot/bzImage root=/dev/sda1 vga=normal 
```
# 最后重启即可
