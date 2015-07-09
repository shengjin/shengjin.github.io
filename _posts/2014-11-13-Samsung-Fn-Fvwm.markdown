---
title: Linux下samsung 900x笔记本的Fn键解决方案
layout: post
tags:
  - linux
  - laptop
  - fvwm
---

困扰我一年的问题！今天晚上通过摸索基本搞定！

(1),在“~/.Xmodmap”中写入：

keycode 222 = XF86MonBrightnessDown

keycode 223 = XF86MonBrightnessUp

keycode 121 = F15

keycode 122 = F16

keycode 123 = F17

keycode 237 = F18

keycode 246 = F20



(2),在“~/.fvwm/.fvwm2rc”中添加：

Key XF86MonBrightnessDown A A Exec xbacklight -dec 10

Key XF86MonBrightnessUp A A Exec xbacklight -inc 10

key F15 A A Exec amixer set Master toggle

key F16 A A Exec amixer set Master 10%-

key F17 A A Exec amixer set Master 10%+


如上解决了 屏幕亮度调节、静音toogle、音量调节、无线toogle6个Fn键。

键盘背光的调节暂时无法通过Fn键的搞定，但是可以通过编辑如下文件手动调节：

/sys/devices/platform/samsung/leds/samsung::kbd_backlight/brightness

数值为 0-8，鉴于背光调节基本用不到，可以暂时无视之。

哈哈哈哈哈哈哈！
