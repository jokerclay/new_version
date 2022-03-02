---
title: "【GDB】错误Undefined"
date: 2021-11-15T21:47:29+08:00
draft: true
---

# Undefined command: "layout".  Try "help".

# 在使用 GDB 调试时出现如下报错

```
$ gdb hello 
GNU gdb (Debian 10.1-2) 10.1.90.20210103-git
Copyright (C) 2021 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from hello...
(gdb)
(gdb) layout src
Undefined command: "layout".  Try "help".
(gdb)
(gdb) exit
Undefined command: "exit".  Try "help".
(gdb) quit
```

## 使用 linux 版本

```
Linux clay 5.10.0-kali9-amd64 #1 SMP Debian 5.10.46-4kali1 (2021-08-09) x86_64 GNU/Linux
```

# 解决方案

```
sudo apt install build-essential gdb
```



# 问题原因

## The default installation from Debian 9's netinst ISO doesn't include gdb or C or C++ compilers. A user would typically run apt install build-essential gdb to install them.

## Debian 9 的 netinst ISO 的默认安装不包括 gdb 或 C 或 C++ 编译器。 用户通常会运行 apt install build-essential gdb 来安装。



## 相关链接 

https://mlog.club/article/5425874
