---
title: gnuplot条件画图与多窗口
layout: post
tags:
  - gnuplot
---


条件画图：

例一：

> plot '1.dat' using 1:($3==0?$2:1/0)

例二：

> plot "1.dat" using 1:(stringcolumn(3) eq "a"? $2:1/0) title "a" lc rgb "blue",\

>  "" using 1:(stringcolumn(3) eq "b"? $2:1/0) title "b" lc rgb "red"


多窗口：

> set term x1 1
> plot sin(x)
> set term x1 2
> plot sin(x)

