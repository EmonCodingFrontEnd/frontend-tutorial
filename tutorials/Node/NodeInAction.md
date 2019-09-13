# Node实战

[返回列表](https://github.com/EmonCodingFrontEnd/frontend-tutorial)

[TOC]

# 官方地址： https://nodejs.org/en/

# 官方文档：https://nodejs.org/en/docs/

# 中文文档：http://nodejs.cn/api/

# npm文档：https://www.npmjs.com/

# editconfig：https://editorconfig.org/

# 一、Node

## 1、CommonJS规范

```shell
# 查找全局依赖安装的位置
npm root -g
```



## 2、global

- CommonJS
- Buffer、process、console
- timer



## 3、调试

- Inspector

- WebStorm自带调试，像调试Java一样简单



## 4、NodeJS基础API

### 4.1、path

- `__dirname`和`__filename`总是返回文件的绝对路径。

- `process.cwd()`总是返回执行node命令所在文件夹。

- `./`
  - 在require方法中总是相对当前文件所在文件夹
  - 在其他地方和process.cwd()一样，相对node启动文件夹。



### 4.2、Buffer

- Buffer用于处理二进制数据流
- 实例类似整数数组，大小固定
- C++代码在V8堆外分配物理内存



## 5、零碎知识

### 5.1、常用模块

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





# 二、NPM

临时：[npm命令详解]( https://www.cnblogs.com/itlkNote/p/6830682.html)

[中文官网](https://www.npmjs.cn/)

## 1、NPM是什么

NPM的全称是`Node Package Manager`，是随同NodeJS一起安装的包管理和分发工具，它很方便让JavaScript开发者下载、安装、上传以及管理已经安装的包。

## 2、NPM模块的版本号

每一个模块后面对应的就是他的版本号，如"^4.10.1"。下面是几个版本的表达式：

| 表达式                     | 版本范围              |
| -------------------------- | --------------------- |
| >=1.2.7                    | 大于等于1.2.7         |
| >=1.2.7<1.3.0              | 1.2.7,1.2.8,1.2.9     |
| 1.2.3-2.3.4                | >=1.2.3<=2.3.4        |
| 1.2-2.3.4                  | >=1.2.0<=2.3.4        |
| 1.2.3-2.3                  | >=1.2.3<2.4.0         |
| 1.2.3-2                    | >=1.2.3<3.0.0         |
| *                          | >=0.0.0               |
| 1.x(等价于1.X)             | >=1.0.0<2.0.0         |
| 1(等价于1.x.x)             | >=1.0.0 <2.0.0        |
| 1.2(等价于1.2.x)           | >=1.2.0 <1.3.0        |
| ~1.2.3(>=1.2.3 <1.(2+1).0) | >=1.2.3 <1.3.0        |
| ~1.2(>=1.2.0 <1.(2+1).0)   | >=1.2.0 <1.3.0        |
| ~1(>=1.0.0 <(1+1).0.0)     | >=1.0.0 <2.0.0        |
| ~0.2.3(>=0.2.3 <0.(2+1).0) | >=0.2.3 <0.3.0        |
| ~0.2(>=0.2.0 <0.(2+1).0)   | >=0.2.0 <0.3.0        |
| ~0(>=0.0.0 <(0+1).0.0)     | >=0.0.0 <1.0.0        |
| ~1.2.3-beta.2              | >=1.2.3-beta.2 <1.3.0 |
| ^1.2.3                     | >=1.2.3 <2.0.0        |
| ^0.2.3                     | >=0.2.3 <0.3.0        |
| ^0.0.3                     | >=0.0.3 <0.0.4        |
| ^1.2.3-beta.2              | >=1.2.3-beta.2 <2.0.0 |
| ^0.0.3-beta                | >=0.0.3-beta <0.0.4   |
| ^1.2.x                     | >=1.2.0 <2.0.0        |
| ^0.0.x                     | >=0.0.0 <0.1.0        |
| ^0.0                       | >=0.0.0 <0.1.0        |
| ^1.x                       | >=1.0.0 <2.0.0        |
| ^0.x                       | >=0.0.0 <1.0.0        |

npm包的版本号格式X.Y.Z，版本号的格式遵循semver 2.0规范，其中X为主版本号，只有更新了不向下兼容的API时修改主版本号；Y为次版本号，当模块增加了向下兼容的功能时进行修改；Z为修订版本号，当模块进行了向下兼容的bug修改后进行修改，这就是**语义化的版本控制**。

### 2.1、脱字符`^`

默认情况下，当用--save或者--save-dev安装模块时，npm通过脱字符（^）来限定所安装模块的`最新的`主版本号，而该脱字符对不同的版本号有不同的更新机制。

- `^1.2.1` 代表的更新版本范围为>=1.2.1&&<2.0.0
- `^0.2.1` 代表的更新版本范围为>=0.2.1&&<0.3.0
- `^0.0.2` 代表的更新版本范围为0.0.2（相当于锁定了0.0.2版本）

### 2.2、波浪号`~`

波浪号`~`会匹配最近的小版本依赖包。

- `~1.2.3`匹配 >=1.2.x<1.3.0
- `~1.2`匹配 >=1.2.0 <1.3.0
- `~1`匹配 >=1.0.0 <2.0.0

## 3、NPM命令

### 3.1、npm install

```she
npm install (with no args, in package dir)
npm install [<@scope>/]<name>
npm install [<@scope>/]<name>@<tag>
npm install [<@scope>/]<name>@<version>
npm install [<@scope>/]<name>@<version range>
npm install <git-host>:<git-user>/<repo-name>
npm install <git repo url>
npm install <tarball file>
npm install <tarball url>
npm install <folder>

aliases: npm i, npm add
common options: [-P|--save-prod|-D|--save-dev|-O|--save-optional] [-E|--save-exact] [-B|--save-bundle] [--no-save] [--dry-run]
```

- 安装指定版本：

```shell
npm install gulp@3.9.1
```

项目对模块的依赖可以使用下面的3种方法来表示（假设当前版本号是1.1.0）：

1. 兼容模块新发布的补丁版本：`~1.1.0`、`1.1.x`、`1.1`

2. 先容模块新发布的小版本、补丁版本：`^1.1.0`、`1.x`、`1`

3. 兼容模块新发布的大版本、小版本、补丁版本：`*`、`x`



- `S,--save`安装包信息将加入到dependencies(生产阶段的依赖）

```shell
npm install gulp --save 
或
npm install gulp -S
```

package.json文件的dependencies字段：

```json
"dependencies": {
    "gulp": "^3.9.1"
}
```



- `-D,--save-dev`安装包信息将加入到devDependencies（开发阶段的依赖），所以开发阶段一般使用ta

```shell
npm install gulp --save-dev 
或
npm install gulp -D
```

package.json文件的devDependencies字段：

```json
"devDependencies": {
    "gulp": "^3.9.1"
}
```



- `-O,--save-optional`安装包信息将加入到optionalDependencies(可选阶段的依赖)

```shell
npm install gulp --save-optional 
或
npm install gulp -O
```

package.json文件的optionalDependencies字段：

```json
"optionalDependencies": {
    "gulp": "^3.9.1
}
```



- `E,--save-exact`精确安装指定模块版本

```shell
npm install gulp --save-exact
或
npm install gulp -E
```

输入命令`npm install gulp -ES`，留意package.json文件的dependencies字段，可以看到版本号中的`^`消失了

```json
"dependencies": {
    "gulp": "3.9.1"
}
```

模块的依赖都被写入了package.json文件后，他人打开项目的根目录（项目开源、内部团队合作），使用`npm install`命令可以根据dependencies配置安装所有的依赖包。

```shell
npm install
```

- 本地安装（local）

```shell
npm install gulp
```

- 全局安装（global），使用`-g`或`--global`

```shell
npm install gulp -g
```



### 3.2、npm uninstall

```shell
npm uninstall [<@scope>/]<pkg>[@<version>]... [-S|--save|-D|--save-dev|-O|--save-optional|--no-save]

aliases: remove, rm, r, un, unlink
```



- 卸载开发版本的模块

```shell
npm uninstall gulp --save-dev
```



### 3.3、npm update

```shell
npm update [-g] [<pkg>...]

aliases: up, upgrade
```

### 3.4、npm outdated

检查模块是否已经过时

```shell
npm outdated [[<@scope>/]<pkg> ...]
```



### 3.5、npm ls

查看安装的模块

```shell
npm ls [[<@scope>/]<pkg> ...]

aliases: list, la, ll
```

查看全局安装的模块及依赖

```bash
npm ls -g
```



### 3.6、npm help

查看某条命令的帮助详情

```shell
npm help <term> [<terms..>]
```



### 3.7、npm config 

管理npm的配置路径

```bash
npm config set <key> <value> [-g|--global]
npm config get <key>
npm config delete <key>
npm config list [-l] [--json]
npm config edit
npm get <key>
npm set <key> <value> [-g|--global]

aliases: c
```

- 设置淘宝镜像

```shell
npm config set registry https://registry.npm.taobao.org
```

- 获取镜像设置

```shell
npm config get registry
```

- 查看配置列表

```shell
npm config list
```

- 删除配置项

```shell
npm config delete <key>
```

- 编辑配置文件

```shell
npm config edit
```

### 3.8、npm cache 

管理模块的缓存

```bash
npm cache add <tarball file>
npm cache add <folder>
npm cache add <tarball url>
npm cache add <name>@<version>

npm cache clean [<path>]
aliases: npm cache clear, npm cache rm

npm cache verify
```

- 清除npm本地缓存

```bash
npm cache clean
```



# 三、YARN

[Yarn中文官网](https://yarn.bootcss.com/)

## 1、YARN是什么

Yarn对你的代码来说是一个包管理器，你可以通过它使用全世界开发者的代码，或者分享自己的代码。Yarn做这些块捷、安全、可靠，所以你不用担心什么。

通过Yarn你可以使用其他开发者针对不同问题的解决方案，使自己的开发过程更简单。使用讴歌过程中遇到问题，你可以将其上报或者贡献解决方案。一旦问题被修复，Yarn会更新保持同步。

代码通过`包（package）（或者称为模块（moudule））`的方式来共享。一个包里包含所有需要共享的代码，以及描述包信息的文件，称为`package.json`。

## 2、使用方法

### 2.1、安装yarn

```bash
npm install -g yarn
yarn --version
```



### 2.2、初始化一个新项目

```bash
yarn init
```



### 2.3、添加依赖包

```bash
yarn add [package]
yarn add [package]@[version]
yarn add [package]@[tag]
```



### 2.4、将依赖项添加到不同依赖项类别中

分别添加到`devDependencies`、`peerDependencies`和`optionalDependencies`类别中：

```bash
yarn add [package] --dev
yarn add [package] --peer
yarn add [package] --optional
```



### 2.5、升级依赖包

```bash
yarn upgrade [package]
yarn upgrade [package]@[version]
yarn upgrade [package]@[tag]
```



### 2.6、移除依赖包

```bash
yarn remove [package]
```



### 2.7、安装项目的全部依赖

```bash
yarn
或
yarn install
```



## 3、YARN命令详解

### 3.1、常用命令

- 创建项目

```bash
yarn init
```

- 安装依赖包

```bash
yarn
或
yarn install
```

- 添加依赖包

```bash
yarn add
```

- 配置淘宝镜像

```bash
yarn config set registry "https://registry.npm.taobao.org"
```





























