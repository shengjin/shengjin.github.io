---
title: Python从字符串中提取数字
layout: post
tags:
  - python
---

示例：

> str = "h3110 23 cat 444.4 rabbit 11 2 dog"

> [int(s) for s in str.split() if s.isdigit()]

> [23, 11, 2]
