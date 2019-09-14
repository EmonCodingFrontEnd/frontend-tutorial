# Vue实战

[返回列表](https://github.com/EmonCodingFrontEnd/frontend-tutorial)

[TOC]

# WebStorm学习笔记

# 一、WebStorm配置

## 1、注册参考

获取注册码的原始引导地址：https://www.jianshu.com/p/133af2e4fe3f

1、注册码：

```
http://idea.lanyus.com/
```

## 2、配置Node

左侧： `Default Settings`->`Languages&Frameworks`->`Node.js and NPM`

右侧：

-  `Node interpreter`: 选择 node.exe 存在的路径，比如：

```
C:\Program Files\nodejs\node.exe
```

- 勾选`Coding assistance for Node.js`
- `Package manager`: 选择包含npm的路径，比如：

```
C:\Program Files\node_modules\npm
```

## 3、调试

## 3.1、安装谷歌访问助手

https://github.com/haotian-wang/google-access-helper

##  3.2、 配置WebStorm

https://www.jianshu.com/p/165db5bb1392

https://blog.csdn.net/coding_lin/article/details/81093890

https://www.jianshu.com/p/ad8c3b480ef3

## 3.3、安装vue-devtools

https://segmentfault.com/a/1190000015363628



# 二、vue-cli

## 1、vue-cli2

### 1.1、安装

```bash
npm install -g vue-cli
或
cnpm install -g vue-cli
```

### 1.2、创建vue-cli项目

```bash
vue init webpack <projectName>
```

安装过程需要注意的点：

- Install vue-router?(Y/n)是否安装vue-router，这是官方的路由，大多数情况下都使用，这里就输入“y”后回车即可。
- Use ESLint to lint your code?(Y/n)是否使用ESLint管理代码，ESLint是个代码风格管理工具，是用来统一代码风格的，一般项目中都会使用。

安装完成后，根据提示启动项目：

```bash
cd <projectName>
npm run dev
```



















<u></u>