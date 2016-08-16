---
title: 查寻硬件在linux内核中的驱动模块
layout: post
tags:
  - linux
  - driver
---


之前因为读manual不认真，没有安装sys-kernel/linux-firmware，
花费了一会儿解决无线网卡的驱动问题，但也因此了解了如何在linux内核源码中
查找硬件对应的驱动模块，记录如下：

首先，列出电脑上所有硬件信息：

> # lspci


然后，根据所要查找的硬件的编号（在每个硬件信息的头一列，如我的无线网卡的对应编号为01:00.0），
进一步查看硬件码：

> # lspci -nv  |grep 01:00.0

我的无线网卡对应的输出：01:00.0 0280: 8086:088e (rev 24)


接下来，进入带内核源码目录，查找该硬件码：

> #  cd /usr/src/linux/drivers/net/wireless/

> #  grep -ri 0x088e * |grep PCI

即可找出对应的驱动模块为iwlwifi。

