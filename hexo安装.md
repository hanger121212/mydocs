---
title: hexo安装
date: 2017-12-06 17:25:20
tags: [安装,hexo]
---

## 安装(先装node)
> npm install -g hexo-cli

## 设置全局
> ln -s /usr/src/node-v8.9.1-linux-x64/bin/hexo /usr/local/bin/hexo

## hello blog
> hexo init blog
> cd blog
> npm install
> hexo server

## 安装主题
> git clone https://github.com/iissnan/hexo-theme-next themes/next