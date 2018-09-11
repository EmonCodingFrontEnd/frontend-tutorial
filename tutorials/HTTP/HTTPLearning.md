# HTTP学习

[返回列表](https://github.com/EmonCodingFrontEnd/frontend-tutorial)

[TOC]

# 一、HTTP协议基础及发展历史

## 1、HTTP协议基础

![网络参考模型](https://github.com/EmonCodingFrontEnd/frontend-tutorial/blob/master/tutorials/HTTP/images/2017082601.png)

- 物理层： 主要作用是定义物理设备如何传输数据
- 数据链路层： 在通信的实体间建立数据链路连接
- 网络层： 为数据在结点之间传输创建逻辑链路
- 传输层： 向用户提供可靠的端到端（End-to-End）服务，向高层屏蔽了下层数据通信的细节
- 应用层： 为应用软件提供了很多服务，构建于TCP/IP协议之上，屏蔽了网络传输相关的细节

## 2、发展历史

- HTTP/0.9
  - 只有一个命令GET
  - 没有HEADER等描述数据的信息
  - 服务器发送完毕，就关闭TCP连接
- HTTP/1.0
  - 增加了很多命令
  - 增加status code和header
  - 多字符集支持、多部分发送、权限、缓存等
- HTTP/1.1
  - 持久连接
  - pipeline
  - 增加host和其他一些命令
- HTTP2
  - 所有数据都是以二进制传输
  - 同一个连接里面发送的请求不需要按照顺序来处理
  - 头信息的压缩以及推送等提高效率的功能

## 3、HTTP的三次握手

### 3.1、三次握手图解

![三次握手图解](https://github.com/EmonCodingFrontEnd/frontend-tutorial/blob/master/tutorials/HTTP/images/2018091101.png)

### 3.2、使用Wireshark抓包

