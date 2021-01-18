---
title: hexo-filter-file-link
date: 2020-08-06 17:11:03
tags: [hexo]
categories: 
  - hexo主题相关
  - 官方插件
---
> 一个插件，可方便地以markdown样式链接本地发布的文件

<!-- more -->

## 安装

cd到hexo root

```
npm install hexo-filter-file-link --save
```

## 例子

这是您的帖子文件：

```
- sources
  |- _post
      |- a.md
      |- c.md
```

然后你想在`a.md`中链接`c.md`

这是 `a.md`的内容：

```
blublublue, this is page [C](file://c.md)
```

在经过`hexo-filter-file-link`的处理后，`a.md`会被翻译成如下代码：

```
blublublue, this is page [C](http://yoursite.com/c)
```

这是在`before_post_render`事件期间捕获的真实网址(‾◡◝)

## 我的示例
```
原文：[【C数据结构】一些准备工作](file://C_Structure.md)
```
```markdown
[【C数据结构】一些准备工作](file://C_Structure.md) 
```
**注意**：在每次`hexo g`之前都应先执行`hexo clean`
