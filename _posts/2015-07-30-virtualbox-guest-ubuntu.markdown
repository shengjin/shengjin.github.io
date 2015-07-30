---
title: Virtualbox里为ubuntu虚拟机设置ShareFolder
layout: post
tags:
  - Virtualbox
---

最近跟教程自学流体模拟，因为archlinux下pyro2运行中可视化显示不正常。
觉得安装个ubuntu虚拟机试试。这里总结下设置sharefolder的步骤。

1, 安装GuestAdditions, 选择Devices -> Install Guest Additions。

2, 在Virtualbox的虚拟机管理页面设置sharefolder，比如我选择创建名为VboxShare的文件夹。

3, 在ubuntu虚拟机中，运行如下命令把sharefolder挂载到指定文件夹：
> sudo mount -t vboxsf -o uid=$UID jin /home/jin/host_jin

