---
title: 'sonar-scanner扫描 Unknown: sonar.projectKey错误'
date: 2019-08-19 05:42:31
categories:
tags: [sonar]
description:
---

使用sonnar-scanner对代码进行扫描时出现如下错误
![Error](https://i.loli.net/2019/08/19/eLmUjWgR6dqlxo7.png)

问题一直困扰了我很久，网上有很多说法，可是尝试了很多方法都找不到原因。
查看sonnar配置
```HTML
<span style="font-family:'KaiTi_GB2312';font-size:24px;">sonar.projectKey=zhihu  
sonar.projectName=zhihu  
sonar.projectVersion=1.0  
sonar.sources=app  
sonar.language=javascript
sonar.sourceEncoding=UTF-8  
</span>
```
发现第一条配置sonar.projectKey和html出现在同一行，调整一下
```HTML
<span style="font-family:'KaiTi_GB2312';font-size:24px;">
sonar.projectKey=zhihu  
sonar.projectName=zhihu  
sonar.projectVersion=1.0  
sonar.sources=app  
sonar.language=javascript
sonar.sourceEncoding=UTF-8  
</span>
```

问题解决
![OK](https://i.loli.net/2019/08/19/qzwAoODuiKsWQpT.png)
