---
title: 搭建⭕⭕服务器
date: 2021-05-19 20:00:00
tags: [工具]
categories: 
  - 资源分享
  - 自制
---

## 前言

简单记录搭建过程...希望不会被请喝茶🍵

## 运行环境

| 服务器     | 腾讯-轻量应用服务器               |
| ---------- | --------------------------------- |
| 系统       | CentOS 7.9.2009(Py3.7.9)          |
| 面板版本   | 宝塔-免费版 7.5.2                 |
| 地域       | 中国香港                          |
| 实例规格   | CPU: 1核，内存: 1GB               |
| 磁盘       | 系统盘：25GB                      |
| 流量包套餐 | 峰值带宽 30Mbps，流量包 1024GB/月 |
| 价格       | 24元/月                           |

## 服务端配置

1. 安装pip

```bash
yum install python-pip
```

2. 安装shadowsocks

```bash
pip install https://github.com/shadowsocks/shadowsocks/archive/master.zip -U
```

安装shadowsocks会遇到的坑：目前最新的客户端(4.4.0.0)仅支持如下加密方式：aes-128-gcm、aes-192-gcm、aes-256-gcm、chacha20-ietf-poly1305、xchacha20-ietf-poly1305，而网上大部分教程仍在使用aes-128-cfb，所以你会尴尬地发现客户端没有与服务端对应的加密方式。解决方法有两个：

- 使用低版本的客户端，例如：4.1.8（过时的加密方式会带来安全隐患）
- 安装最新的服务端（3.0.0）参考链接👉[求教如何让ss客户端支持aes-256-gcm加密方式 - (ubuntukylin.com)](https://www.ubuntukylin.com/ukylin/forum.php?mod=viewthread&tid=188059)，也就是使用上面的pip命令安装。

3. 安装Supervisor管理器 2.2

- 略

4. 启动服务

- 打开Supervisor管理器->添加守护进程->填写如下启动命令->确定

```bash
ssserver -s 0.0.0.0 -p 23333 -k <password> -m aes-256-gcm	
```

## 客户端配置

1. 安装最新的客户端：[Releases · shadowsocks/shadowsocks-windows (github.com)](https://github.com/shadowsocks/shadowsocks-windows/releases/)
2. 填写服务器地址、端口、密码、加密方式，Done！
