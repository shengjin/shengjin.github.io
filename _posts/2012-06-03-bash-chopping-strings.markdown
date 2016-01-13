---
title: Bash截断字符
layout: post
tags:
  - bash
---

懒得解释，示例说话：

例一：

> $ MYVAR=foodforthought.jpg
> $ echo ${MYVAR##\*fo}
> rthought.jpg
> $ echo ${MYVAR#\*fo}
> odforthought.jpg

例二：

> $ MYFOO="chickensoup.tar.gz"
> $ echo ${MYFOO%%.\*}
> chickensoup
> $ echo ${MYFOO%.\*}
> chickensoup.tar

例三：

> $ EXCLAIM=cowabunga
> $ echo ${EXCLAIM:0:3}
> cow
> $ echo ${EXCLAIM:3:7}
> abunga

