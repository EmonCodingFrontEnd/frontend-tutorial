# Node实战

[返回列表](https://github.com/EmonCodingFrontEnd/frontend-tutorial)

[TOC]

# 官方地址： https://nodejs.org/en/

# 官方文档：https://nodejs.org/en/docs/

# 中文文档：http://nodejs.cn/api/

# npm文档：https://www.npmjs.com/

# editconfig：https://editorconfig.org/

# 一、CommonJS规范

```shell
# 查找全局依赖安装的位置
npm root -g
```



# 二、global

- CommonJS
- Buffer、process、console
- timer



# 三、调试

- Inspector

- WebStorm自带调试，像调试Java一样简单



# 四、NodeJS基础API

## 1、path

- `__dirname`和`__filename`总是返回文件的绝对路径。

- `process.cwd()`总是返回执行node命令所在文件夹。

- `./`
  - 在require方法中总是相对当前文件所在文件夹
  - 在其他地方和process.cwd()一样，相对node启动文件夹。



## 2、Buffer

- Buffer用于处理二进制数据流
- 实例类似整数数组，大小固定
- C++代码在V8堆外分配物理内存



# 零碎知识

## 1、常用模块

- chalk

颜色代码模块

```shell
npm install chalk --save
```

- supervisor

1. 安装

```shell
npm install supervisor -g
```

2. 使用

```shell
supervisor app.js // app.js是一个node的server文件
```

- handlebars

```shell
npm install handlebars --save
```









