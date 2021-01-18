---
title: 在Docker制作Django-3.1.1镜像
date: 2020-09-19 19:56:22
tags: [Django, Docker]
categories:
  - 神兵利器
  - docker
---
> 出大问题，DaoCloud提供的Django镜像是1.7，据说还是同步Docker Hub的包，拉跨
> 一看居然是2016年的项目，拉跨

<!--more-->

## 制作Django-3.1.1镜像


**windows PC**
Windows 的 Docker 桌面版和 Docker Toolbox 已经包括 Compose 和其他 Docker 应用程序
因此 Windows 用户不需要单独安装 Compose
Docker 安装说明可以参阅 Windows Docker 安装

## 参考链接
- [Django 文档](https://docs.djangoproject.com/zh-hans/3.1/) 
- [在docker中使用django](https://docs.docker.com/compose/django/) 
- [Docker Compose](https://www.runoob.com/docker/docker-compose.html) 
- [Docker容器化部署python应用](https://zhuanlan.zhihu.com/p/71251233) 
- [Cenos7环境下使用Docker部署Django+nginx+uwsgi环境](https://www.cnblogs.com/Felix-DoubleKing/p/11531678.html) 