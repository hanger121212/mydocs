---
title: Shadowsocks安装
date: 2017-11-07 17:25:20
tags: [shadowsocks,安装]
---

##安装shadowsocks(阿里云)
> yum install python-setuptools && easy_install pip
> pip install shadowsocks

##配置文件
> vim /etc/shadowsocks.json
> {
>   "server":"your_server_ip",
>   "server_port":8388,
>   "password":"yourpassword",
>   "timeout":300,
>   "method":"aes-256-cfb",
>   "fast_open":false,
>   "workers": 1
> }

## 启动
> ssserver -c /etc/shadowsocks.json -d start

###### 记得修改阿里云服务器安全组,增加入站端口号