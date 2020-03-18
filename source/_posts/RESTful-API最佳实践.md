---
title: RESTful API最佳实践
date: 2019-07-10 00:42:06
categories:
tags: [node学习笔记, koa]
description:
---

**增删改查应该返回什么相应？**

+ 查：查列表返回单个数组。查单个信息返回数组中的某一项
+ 增，改：返回当前增加或者修改的数据
+ 删：204状态码

以上是REST的最佳实践，并不是硬性要求。

```javascript
usersRouter.get('/', (ctx)=>{
    ctx.body = [name: '李雷', name: '韩梅梅']
})
usersRouter.post('/:id', (ctx)=>{
    ctx.body = [name: '李雷', name: '韩梅梅']
})
```

