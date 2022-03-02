---
title: "【Linux】SSH"
date: 2021-11-27T19:16:49+08:00
draft: true
---

# SSH

## 1. 有时候我们的 linux 机器默认 SSH 是不开机 自启动的

## 将 SSH 服务设置为开机自启 ，命令

```
systemctl enable ssh.service
```

## 2. SSH config

## 一般 SSH 登录命令为：

```
ssh UserName@ip_address
```

## 比如：

```
ssh clay@192.168.1.110
```

## 每次登录都要输入一大串，可以设置   .ssh/config 文件 进行简化操作， 没有 config 的话，创建一个

## .ssh/config :

## 

```
Host name(可任意取一个名字)
  HostName 远程主机名/域名/IP 地址
  User 用户名
  ...
  其他的配置
```

## 我的 .ssh/config :

```
Host dev
  HostName 192.168.1.110
  User clay
  #  RemoteCommand tmux	# 用于登录自动进入 tmux
  RequestTTY yes
```



## 3. 关于免密登录

（1）生成SSH密钥和公钥

```
ssh-keygen -b 4096 -t rsa
```

获得文件

```
id_rsa.pub
id_rsa
```

（2）将公钥 拷贝到远程服务器上  的 ./ssh/authorized_keys 中



## 踩坑

（1） 在获取 SSH密钥和公钥 时，有会要求你输入 一个 `短语` 回车就好，如果输入了话，下次登录时 还要输入，很不方便

（2）将公钥 拷贝到远程服务器上  的 ./ssh/authorized_keys 中 后，要 给 ssh 文件夹 和 authorized_keys 配置权限

```
chmod 700 .ssh
```

```
chmod 600 ./authorized_keys
```

