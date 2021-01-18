---
title: 一次Hackintosh记录
date: 2020-09-15 21:25:54
tags: [Hackintosh]
categories: Hackintosh
---
记录令人心醉的黑苹果之旅~

在淘宝花了300请人装黑苹果，手贱更新了系统导致无法正常引导
索性从零开始亲自折腾，防止再次出现类似状况

Do it yourself!

<!--more-->

## 废话
早闻Mac系统大名，却苦于纠结选择Mac与PC，理由自然不用多述
在我纠结买哪个时，发现XPS的设计与Macbook相近，并且相同价位配置更高
于是错过了离Macbook最近的一次机会😥

如今已过去两年，加上自己配了台式机作为主力，我想是时候拔草了
开开心心的上淘宝找了家据说有十年历史的“老店”，安装过程挺顺利，等了这么多年终于能一睹macOS的芳容，真香~

<img src="https://cdn.jsdelivr.net/gh/Sknp1006/cdn@master/img/anime/great.jpg" style="zoom:80%;" />

但是新系统并不是最新的，系统更新的红点就像鱼饵一样诱鱼，于是悲剧发生了——

> 本文不是教程向，详细教程参考本文给出的链接即可

## 预备知识

colver使用教程: [https://blog.daliansky.net/clover-user-manual.html](https://blog.daliansky.net/clover-user-manual.html) 

macOS安装教程: [https://blog.daliansky.net/MacOS-installation-tutorial-XiaoMi-Pro-installation-process-records.html](https://blog.daliansky.net/MacOS-installation-tutorial-XiaoMi-Pro-installation-process-records.html) 

长期维护机型清单: [Hackintosh黑苹果长期维护机型整理清单](https://blog.daliansky.net/Hackintosh-long-term-maintenance-model-checklist.html) 

相关网站: 

- [黑苹果乐园](https://imac.hk/) 
- [黑果小兵的部落阁](https://blog.daliansky.net/) 
- 远景论坛
- ...

本文参考链接: [https://github.com/LuletterSoul/Dell-XPS15-9570-macOS](https://github.com/LuletterSoul/Dell-XPS15-9570-macOS) 
视频链接(转载): [https://www.bilibili.com/video/bv1Yv411C7rp](https://www.bilibili.com/video/bv1Yv411C7rp) 

## 开始折腾

### 安装方式

淘宝使用Windows+macOS双系统的方式，这种安装方式方便技术人员远程操作，也方便小白后期使用Windows的需求

对于我来说，XPS作为备用机只装macOS就挺好😃

### 硬件配置

> 型号: Dell XPS 9570
> 处理器: Intel Core i7-8750H
> Intel集显: UHD630
> 内存: Micron 8ATF1G64HZ-2G6E1 8GB* 2
> 显示器: 1080p Sharp Display
> 固态硬盘: PC401 NVMe SK hynix 512GB SSD
> 触摸板: Synaptics SYNA2393
> 音频: Realtek ALC298
> 无线+蓝牙: Killer 1535(无线x 蓝牙√)
> 指纹识别器: Goodix fingerpint reader(x)
> 独显: Nvidia Geforce 1050Ti(x)

---

![](https://cdn.jsdelivr.net/gh/Sknp1006/cdn@master/img/anime/tobecontinued.jpg) 