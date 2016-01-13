---
title: 在Bash中给变量补零
layout: post
tags:
  - linux
  - bash
---



```
for i in $(seq -f "%05g" 10 15)
do
  echo $i
done
```



```
$ i=99
$ printf -v j "%05d" $i
$ echo $j
00099
```

