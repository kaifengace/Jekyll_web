---
layout: page
title: DNS 学习笔记整理
categories:
     - 学习笔记
---

DNS一种能进行主机名到IP地址转换的目录服务，这就是域名系统（Domain Name System），DNS协议运行在UDP之上，使用端口53.

DNS提供的服务有：
- 主机别名，规范主机名。应用程序可以掉用DNS来获得主机名对应的规范主机名一级主机的IP地址。
- 邮件服务器别名。电子邮件应用程序可以调用DNS，对提供的邮件服务器别名进行解析，以获得该主机的规范主机名及其IP地址。
- 负载分配。

### DNS工作机理
DNS采用分布式设计方案，DNS服务器分为四类：

- 根DNS服务器。
- 顶级域DNS服务器。这些服务器负责顶级域名，如com，org，net，edu- - 和gov以及国家的顶级域名，如uk，fr，ca，jp。
- 权威DNS服务器。这些服务器记录了主机名到IP地址的映射关系。
- 本地DNS服务器（local DNS server）

DNS查询有两种方式：
- 递归查询
- 迭代查询

从请求主机到本地DNS服务器的查询是递归的，其余的查询是迭代的。
DNS广泛的使用了DNS缓存，类似于HTTP缓存服务器。使用本地存储器作为DNS缓存服务器，每当本地服务器从某个DNS服务器接收到一个回答，它能够缓存包含在该回答中的任何信息。
