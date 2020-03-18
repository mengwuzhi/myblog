---
title: koa获取http请求参数
date: 2019-07-11 00:32:20
categories:
tags: [node, koa]
description: nodejs,koa学习笔记
---

## 获取query

>GET http://localhost:3000/users?id=23122


?以后的部分可以被解析为query
```javascript
router.put('/users', (ctx)=> console.log(ctx.query));
```
打印结果
```
Object {id: "23122"}
```

## 获取body请求体

>POST http://localhost:3000/users?id=23122 
>body:{"a":1,"b":2}

因为在koa中需要安装中间件才可以获取请求体，所以选择中间件koa-bodyparse

```javascript
// 声明中间件
const bodyParser = require('koa-bodyparser');

router.post('/users', (ctx)=> console.log(ctx.request.body));

app.use(bodyParser());
```
值得一提的是，`app.use(bodyParser());`必须在`app.use(router.routes());`之前进行调用，否则无法生效

## 获取header

>POST http://localhost:3000/users?id=23122

操作代码
```javascript
router.post('/users', (ctx)=> console.log(ctx.header));
```
打印结果

>accept:"*/*"
>accept-encoding:"gzip, deflate, br"
>accept-language:"zh-CN,zh;q=0.9"
>connection:"keep-alive"
>content-length:"13"
>content-type:"application/json"
>host:"localhost:3000"
>origin:"chrome-extension://aejoelaoggembcahagimdiliamlcdmfm"






