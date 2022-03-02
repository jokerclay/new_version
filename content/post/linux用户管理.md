---
title: "Linux用户管理"
date: 2021-09-16T09:18:36+08:00
draft: true
---

# 1. 添加用户

```bash
adduser userName
```

* example

```
~~>:~ $ sudo adduser king418
Adding user `king418' ...
Adding new group `king418' (1001) ...
Adding new user `king418' (1001) with group `king418' ...

Creating home directory `/home/king418' ...
Copying files from `/etc/skel' ...
New password:
Retype new password:
passwd: password updated successfully
Changing the user information for king418
Enter the new value, or press ENTER for the default
        Full Name []:
        Room Number []:
        Work Phone []:
        Home Phone []:
        Other []:
Is the information correct? [Y/n] y
```



# 2. 切换到某一用户

```
su - userName
```



# 3. 将某一用户 添加到 sudo group

```bash
adduser username sudo
```

* example

```
~~>:~ $ sudo adduser king418 sudo
Adding user `king418' to group `sudo' ...
Adding user king418 to group sudo
Done.
```





# 4. 如果 使用的 Linux 发行版 没有 adduser 命令，或者想对 user 有 更好的 contorl  可以使用 `useradd`



## （1）添加用户

```bash
useradd username
```

