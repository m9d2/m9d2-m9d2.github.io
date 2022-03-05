---
layout: post
title: Ubuntu Server 配置 Shadowsocks-libev 服务端
date: 2020-05-23 18:37:00 +0800
img:  # Add image post (optional)
tags: [Shadowsocks] # add tag
---

> 官方文档：https://github.com/shadowsocks/shadowsocks-libev#debian--ubuntu

## 安装依赖及软件
```shell
$ sudo apt-get install software-properties-common -y
$ sudo add-apt-repository ppa:max-c-lv/shadowsocks-libev -y
$ sudo apt-get update
$ sudo apt install shadowsocks-libev
```

## 配置config.json

```shell
$ sudo vim /etc/shadowsocks-libev/config.json
```

> 参考如下配置内容

```shell
{
    "server":"0.0.0.0",
    "server_port":8488,
    "local_port":1080,
    "password":"123456",
    "timeout":60,
    "method":"aes-256-cfb"
}
```
## 启动服务

```shell
# Start the service
$ sudo /etc/init.d/shadowsocks-libev start    # for sysvinit, or
$ sudo systemctl start shadowsocks-libev      # for systemd
```

## 重启服务

```shell
$ sudo systemctl restart shadowsocks-libev 
```
## 查看服务状态

```shell
$ sudo systemctl status shadowsocks-libev 
```





