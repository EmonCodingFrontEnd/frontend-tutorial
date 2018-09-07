# npm实战

[返回列表](https://github.com/EmonCodingFrontEnd/frontend-tutorial)

[TOC]

临时：[npm命令详解]( https://www.cnblogs.com/itlkNote/p/6830682.html)

临时： [11个你应该知道的npm技巧](https://www.jianshu.com/p/aa84b7b35094)

临时：[npm版本的解析](https://www.cnblogs.com/blackgan/p/7828047.html)

# 一、npm常用命令详解

## 1、npm是什么

NPM的全称是Node Package Manager，是随同NodeJS一起安装的包管理和分发工具，它很方便让JavaScript开发者下载、安装、上传以及管理已经安装的包。

官方地址： https://www.npmjs.com/

## 2、npm模块的版本号

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

默认情况下，当用--save或者--save-dev安装模块时，npm通过脱字符（^）来限定所安装模块的主版本号，而该脱字符对不同的版本号有不同的更新机制。

- `^1.2.1` 代表的更新版本范围为>=1.2.1&&<2.0.0
- `0.2.1` 代表的更新版本范围为>=0.2.1&&<0.3.0
- `^0.0.2` 代表的更新版本范围为0.0.2（相当于锁定了0.0.2版本）

## 3、npm install安装模块

- 简介

```shell
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

alias: npm i
common options: [-P|--save-prod|-D|--save-dev|-O|--save-optional] [-E|--save-exact] [-B|--save-bundle] [--no-save] [--dry-run]
```

### 3.1、本地安装

- 安装最新版本

安装最新版本的依赖到本地的node_modules文件夹，并添加到package.json文件的dependencies中

```shell
npm install <name>
```

- 安装指定版本

安装指定版本的依赖到本地的node_modules文件夹，并添加到package.json文件的dependencies中

```shell
npm install <name>@<version>
```

- `-S,--save` 

安装包信息将加入到package.json文件的dependencies中（生产阶段的依赖）

```shell
npm install <name> --save 或者 npm install <name> -S
```

- `-D,--save-dev` 

安装包信息将加入到package.json文件的devDependencies中(开发阶段的依赖)，所以开发阶段一般使用它

```shell
npm install <name> --save-dev 或者 npm install <name> -D
```

- `-O,save-optional` 

安装包信息将加入到package.json文件的optionalDependencies中（可选阶段的依赖）

- `-E,--save-exact`

精确安装指定模块版本

```shell
npm install <name> --save-exact 或者 npm install <name> -E
```

输入命令`npm install <name> -ES`,留意package.json文件的dependencies字段，以看出不好中的`^`消失了。



模块的依赖都被写入package.json文件之后，其他人打开项目的根目录（项目开源、内部团队合作），使用`npm install`命令可以根据dependencies配置安装所有的依赖包。

- 只安装dependencies里面的包

```shell
npm install --production
```

- 只安装devDependencies里面的包

```shell
npm install --dev
```

- 安装dependencies和devDependencies里面包

```shell
npm install
```

### 3.2、全局安装

```shell
npm install <name> -g 或者 npm install <name> --global
```

## 4、npm uninstall卸载模块

- 简介

```shell
npm uninstall [<@scope>/]<pkg>[@<version>]... [-S|--save|-D|--save-dev|-O|--save-optional|--no-save]

aliases: remove, rm, r, un, unlink
```

**把安装命令的install->uninstall，其他保持不变即可**

- 卸载开发版本的模块

```shell
npm uninstall <name> --save-dev
```

**特殊**

- 卸载模块但不移除package.json

```shell
npm uninstall <name> --no-save
```



## 5、npm update更新模块

- 简介

```shell
npm update [-g] [<pkg>...]

aliases: up, upgrade
```



