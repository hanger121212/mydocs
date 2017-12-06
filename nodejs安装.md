---
title: nodejs安装
date: 2017-12-05 17:25:26
tags: [nodejs,安装]
---

## 下载并解压

> wget https://nodejs.org/dist/v8.9.1/node-v8.9.1-linux-x64.tar.gz
> tar zxf node-v8.9.1-linux-x64.tar.gz

## 设置全局
> ln -s /usr/src/node-v8.9.1-linux-x64/bin/node /usr/local/bin/node
> ln -s /usr/src/node-v8.9.1-linux-x64/bin/npm /usr/local/bin/npm

## 测试
> node -v

## 设置镜像地址(npm国内太卡)
> npm config set registry http://registry.npm.taobao.org

## 检查修改结果
> npm config get registry
