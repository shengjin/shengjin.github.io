---
title: 每天根据bing的图片更改桌布的bash脚本
layout: post
tags:
  - bash
  - linux
---

```
#! /bin/bash

today=`date +%Y-%m-%d`

title=${today}.jpg

if [ -e $title ]

then

        exit 1

else

        wget http://cn.bing.com -O index.html

        picture_url=`cat index.html | grep -Po 'http://.*?jpg' | head -n1`

        wget $picture_url -O $title

        convert $title /home/jin/.fvwm/images/wallpaper/background.png

        rm index.html

fi
```

然后放到crontab里面，设成没小时执行一次

