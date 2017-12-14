---
title: koa2填坑
date: 2017-12-14 14:28:21
tags: [填坑,koa,nodejs框架]
---

## koa2安装

```python
# 初始化package.json
npm init

# 安装koa2 
npm install koa
```

## hello world

```javascript
const Koa = require('koa')
const app = new Koa()

app.use( async ( ctx ) => {
  ctx.body = 'hello koa2'
})

app.listen(3000)
console.log('[demo] start-quick is starting at port 3000')
```

## 启动demo

```
node index.js
```

