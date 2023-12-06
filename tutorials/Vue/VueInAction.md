# Vue实战

[返回列表](https://github.com/EmonCodingFrontEnd/frontend-tutorial)

[TOC]

# 二、vue-cli

## 1、安装Vue Cli 5.x

- 前提：

Node.js ^12.0.0 || >= 14.0.0

- 安装：

```shell
$ npm i -g @vue/cli
```

- 升级

如需升级全局的Vue Cli包，请原型。

```shell
$ npm update -g @vue/cli
```

- 创建项目

```shell
$ vue create vue_test
```

- 启动项目

```shell
$ cd vue_test
$ npm run serve
```

- 查看配置

```shell
$ vue inspect > output.js
```



## 2、小贴士

- 地址栏中，经常出现#，是什么作用，能不能去掉#？
- hash模式：地址栏包含#符号，#以后的不被后台获取
- history模式：具有对url历史记录进行修改的功能
- 在微信支付、分享url作为参数传递时，#不能满足需求
- history需要后台配置，处理404的问题。



## Vue2和Vue3声明周期对比

```bash
// mapping vue2 to vue3
beforeCreate -> use setup()
created -> use setup()
beforeMount -> onBeforeMount
mounted -> onMounted
beforeUpdate -> onBeforeUpdate
updated -> onUpdated
beforeDestroy -> onBeforeUnmount
destroyed -> onUnmounted
activated -> onActivated
deactivated -> onDeactivated
errorCaptured -> onErrorCaptured

// added
onRenderTracked
onRenderTriggered
```



# 九、常见问题

## 1、git bash 使用 vue-cli 创建项目无法切换选项

配置`~/.bashrc`：

```bash
alias vue='winpty vue.cmd'
```

