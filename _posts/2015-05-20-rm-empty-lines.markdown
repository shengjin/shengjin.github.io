---
title: vi/sed/awk删除空行
layout: post
tags:
  - linux
---

vi:
> g/^\s\*$/d

sed:
> sed '/^$/d' myFile

awk:
> awk 'NF > 0' filename



