# DNS部署与安全

## 域名组成概述

www.sina.com.cn www为主机名 sina.com.cn为域名

~~~
www.baidu.com.
.为根域
.com为顶级域名
baidu为一级域名
www为主机名
~~~

~~~
FQDN=主机名.DNS后缀
FQDN（完整合格的域名）
~~~

## 监听端口

~~~
TCP53
UDP53
~~~

## DNS解析种类

ipconfig /flushdns(清除本地缓存)

ipconfig /displaydns(显示dns缓存)

##域名解析记录类型

A记录：正向解析记录

CNAME记录：别名

PTR记录：反向解析记录

MX：邮件交换记录

NS：域名服务器解析

## 反向DNS

nslookup手工解析时，回进行一个反向解析

## DNS服务区分类

主要名称服务器

辅助名称服务器

根服务名称服务器

高速缓存名称服务器

## 客户机域名请求解析顺序

DNS缓存—本地hosts文件—找本地DNS服务器

