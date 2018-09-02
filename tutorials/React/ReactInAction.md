# React实战

[返回列表](https://github.com/EmonCodingFrontEnd/frontend-tutorial)

[TOC]

# WebStorm学习笔记

# 一、安装nvm

下载地址： https://github.com/coreybutler/nvm-windows/releases

1. 下载 nvm-setup.zip
2. 安装nvm
3. 配置镜像

打开nvm安装路径，找到nvm目录下的settings.txt文件，追加如下内容

```
node_mirror: https://npm.taobao.org/mirrors/node/
npm_mirror: https://npm.taobao.org/mirrors/npm/
```

https://blog.csdn.net/qq_36423639/article/details/70230571



# 二、安装配置node环境

## 1、安装node和npm

nodejs官网：https://nodejs.org/en/

npmjs官网： https://www.npmjs.com/

1. 打开cmd
2. 在官网查看可安装版本

https://nodejs.org/zh-cn/

3. 安装

安装长期维护版本，推荐多数用户使用（LTS）

**推荐在Linux环境通过nvm ls-remote查看LTS版本安装**

```powershell
nvm install v8.11.3
# 或者
nvm install v6.14.3
```

**以上安装，会按照node和对应的npm版本**

4. 使用

```powershell
nvm use v8.11.3
# 或者
nvm use v6.14.3
```

5. 校验

```powershell
node --version
npm --version
```

## 2、配置淘宝npm镜像【推荐】

```shell
npm config set registry https://registry.npm.taobao.org
```

说明： 配置后可以通过如下方式来校验是否配置成功

`npm config get registry`  或者 `npm info express`

备注：该配置方式，在使用`nvm use <version>`切换了node版本后，还是生效的，是全局的。

## 3、配置cnpm镜像

```shell
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

## 4、npm的使用

### 4.1、npm几种安装第三方包方式的差别

非全局安装：

- 方式一：npm install X
  - 会安装X到node_modules目录中
  - 不会修改package.json
  - 之后运行npm install命令时，不会自动安装X
- 方式二：npm install X --save
  - 会安装X到node_modules目录中
  - 会在package.json的dependencies属性下添加X
  - 之后运行npm install命令时，会自动安装X到 node_modules 目录中
  - 之后运行npm install --production或者标明NODE_ENV变量值为production时，会自动安装msbuild到node_modules目录中
- 方式三：npm install X --save-dev
  - 会安装X到node_modules目录中
  - 会在package.json的devDependencies属性下添加X
  - 之后运行npm install命令时，会自动安装X到 node_modules 目录中
  - 之后运行npm install --production或者标明NODE_ENV变量值为production时，不会自动安装msbuild到node_modules目录中

**使用原则：运行时用到的包使用--save，否则使用--save-dev**

全局安装：

```shell
npm install -g
```

将安装包放在/usr/local下或者你node的安装目录。

可以在命令行直接使用。

### 4.2、npm卸载第三方包

```shell
npm uninstall react --save
```



### 4.3、npm更新第三方包

```shell
npm update --save
```



### 4.4、安装prop-types插件

1. 插件介绍地址： https://www.npmjs.com/package/prop-types
2. 安装

```shell
npm install --save prop-types
```

3. 导入

```shell
import PropTypes from 'prop-types'; // ES6
var PropTypes = require('prop-types'); // ES5 with npm
```

### 4.5、安装antd插件

官网： https://ant.design/index-cn

开箱即用的高质量React组件。

```shell
npm install antd --save
```

### 4.6、安装axios插件

一个基于promise的http库，可以用在浏览器和node.js中。

```shell
npm install axios --save
```

### 4.7、安装react-transition-group

一个动画插件。

```bash
npm install react-transition-group --save
```

### 4.8、安装Charles工具

地址： https://www.charlesproxy.com/download/

Charles其实是一款代理服务器，通过过将自己设置成系统（电脑或者浏览器）的网络访问代理服务器，然后截取请求和请求结果达到分析抓包的目的。该软件是用Java写的，能够在Windows，Mac，Linux上使用。安装Charles的时候要先装好Java环境。

### 4.9、安装redux

```shell
npm install redux --save
```

### 4.10、安装redux-thunk

redux中间件

```shell
npm install --save redux-thunk
```

![2018082502](https://github.com/EmonCodingFrontEnd/frontend-tutorial/blob/master/tutorials/React/images/2018082502.png)

### 4.11、安装redux-saga

redux中间件

```shell
npm install --save redux-saga
```

### 4.12、安装react-redux

资料：

- 英文： http://redux.js.org/
- 中文：http://cn.redux.js.org/

```shell
npm install --save react-redux
```

![2018082501](https://github.com/EmonCodingFrontEnd/frontend-tutorial/blob/master/tutorials/React/images/2018082501.png)



### 4.13、安装styled-components

```shell
npm install --save styled-components
```

### 4.14、安装immutable

https://facebook.github.io/immutable-js/docs/#/

```shell
npm install --save immutable
```

### 4.15、安装redux-immutable

http://facebook.github.io/immutable-js/docs/#/

```shell
npm install --save redux-immutable
```

### 4.16、安装react-router-dom

```shell
npm install --save react-router-dom
```

### 4.17、安装react-loadable

```shell
npm install --save react-loadable
```



## 5、yarn

与npm的对比：

| npm                            | yarn                                 |
| ------------------------------ | ------------------------------------ |
| npm init [-y]                  | yarn init [-y]交互式创建package.json |
| npm install                    | yarn                                 |
| npm install react --save       | yarn add react                       |
| npm uninstall react --save     | yarn remove react                    |
| npm install react --save-dev   | yarn add react --dev                 |
| npm update --save [package]    | yarn upgrade [package]               |
| npm install react --global\|-g | yarn global add react                |
| npm cache clean                | yarn cache clean                     |
| npm run                        | yarn run                             |
| npm start                      | yarn start                           |
| npm test                       | yarn test                            |

### 5.1、安装yarn

```shell
npm install -g yarn
yarn --version
```













# 三、WebStorm配置

## 1、注册参考

WebStrom注册参考： https://blog.csdn.net/zajule/article/details/80674599

1. 修改hosts文件后，使用注册码：

```
0.0.0.0 account.jetbrains.com
```

2. 注册码：

```
EB101IWSWD-eyJsaWNlbnNlSWQiOiJFQjEwMUlXU1dEIiwibGljZW5zZWVOYW1lIjoibGFuIHl1IiwiYXNzaWduZWVOYW1lIjoiIiwiYXNzaWduZWVFbWFpbCI6IiIsImxpY2Vuc2VSZXN0cmljdGlvbiI6IkZvciBlZHVjYXRpb25hbCB1c2Ugb25seSIsImNoZWNrQ29uY3VycmVudFVzZSI6ZmFsc2UsInByb2R1Y3RzIjpbeyJjb2RlIjoiSUkiLCJwYWlkVXBUbyI6IjIwMTgtMTAtMTQifSx7ImNvZGUiOiJSUzAiLCJwYWlkVXBUbyI6IjIwMTgtMTAtMTQifSx7ImNvZGUiOiJXUyIsInBhaWRVcFRvIjoiMjAxOC0xMC0xNCJ9LHsiY29kZSI6IlJEIiwicGFpZFVwVG8iOiIyMDE4LTEwLTE0In0seyJjb2RlIjoiUkMiLCJwYWlkVXBUbyI6IjIwMTgtMTAtMTQifSx7ImNvZGUiOiJEQyIsInBhaWRVcFRvIjoiMjAxOC0xMC0xNCJ9LHsiY29kZSI6IkRCIiwicGFpZFVwVG8iOiIyMDE4LTEwLTE0In0seyJjb2RlIjoiUk0iLCJwYWlkVXBUbyI6IjIwMTgtMTAtMTQifSx7ImNvZGUiOiJETSIsInBhaWRVcFRvIjoiMjAxOC0xMC0xNCJ9LHsiY29kZSI6IkFDIiwicGFpZFVwVG8iOiIyMDE4LTEwLTE0In0seyJjb2RlIjoiRFBOIiwicGFpZFVwVG8iOiIyMDE4LTEwLTE0In0seyJjb2RlIjoiUFMiLCJwYWlkVXBUbyI6IjIwMTgtMTAtMTQifSx7ImNvZGUiOiJDTCIsInBhaWRVcFRvIjoiMjAxOC0xMC0xNCJ9LHsiY29kZSI6IlBDIiwicGFpZFVwVG8iOiIyMDE4LTEwLTE0In0seyJjb2RlIjoiUlNVIiwicGFpZFVwVG8iOiIyMDE4LTEwLTE0In1dLCJoYXNoIjoiNjk0NDAzMi8wIiwiZ3JhY2VQZXJpb2REYXlzIjowLCJhdXRvUHJvbG9uZ2F0ZWQiOmZhbHNlLCJpc0F1dG9Qcm9sb25nYXRlZCI6ZmFsc2V9-Gbb7jeR8JWOVxdUFaXfJzVU/O7c7xHQyaidCnhYLp7v32zdeXiHUU7vlrrm5y9ZX0lmQk3plCCsW+phrC9gGAPd6WDKhkal10qVNg0larCR2tQ3u8jfv1t2JAvWrMOJfFG9kKsJuw1P4TozZ/E7Qvj1cupf/rldhoOmaXMyABxNN1af1RV3bVhe4FFZe0p7xlIJF/ctZkFK62HYmh8V3AyhUNTzrvK2k+t/tlDJz2LnW7nYttBLHld8LabPlEEjpTHswhzlthzhVqALIgvF0uNbIJ5Uwpb7NqR4U/2ob0Z+FIcRpFUIAHEAw+RLGwkCge5DyZKfx+RoRJ/In4q/UpA==-MIIEPjCCAiagAwIBAgIBBTANBgkqhkiG9w0BAQsFADAYMRYwFAYDVQQDDA1KZXRQcm9maWxlIENBMB4XDTE1MTEwMjA4MjE0OFoXDTE4MTEwMTA4MjE0OFowETEPMA0GA1UEAwwGcHJvZDN5MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAxcQkq+zdxlR2mmRYBPzGbUNdMN6OaXiXzxIWtMEkrJMO/5oUfQJbLLuMSMK0QHFmaI37WShyxZcfRCidwXjot4zmNBKnlyHodDij/78TmVqFl8nOeD5+07B8VEaIu7c3E1N+e1doC6wht4I4+IEmtsPAdoaj5WCQVQbrI8KeT8M9VcBIWX7fD0fhexfg3ZRt0xqwMcXGNp3DdJHiO0rCdU+Itv7EmtnSVq9jBG1usMSFvMowR25mju2JcPFp1+I4ZI+FqgR8gyG8oiNDyNEoAbsR3lOpI7grUYSvkB/xVy/VoklPCK2h0f0GJxFjnye8NT1PAywoyl7RmiAVRE/EKwIDAQABo4GZMIGWMAkGA1UdEwQCMAAwHQYDVR0OBBYEFGEpG9oZGcfLMGNBkY7SgHiMGgTcMEgGA1UdIwRBMD+AFKOetkhnQhI2Qb1t4Lm0oFKLl/GzoRykGjAYMRYwFAYDVQQDDA1KZXRQcm9maWxlIENBggkA0myxg7KDeeEwEwYDVR0lBAwwCgYIKwYBBQUHAwEwCwYDVR0PBAQDAgWgMA0GCSqGSIb3DQEBCwUAA4ICAQC9WZuYgQedSuOc5TOUSrRigMw4/+wuC5EtZBfvdl4HT/8vzMW/oUlIP4YCvA0XKyBaCJ2iX+ZCDKoPfiYXiaSiH+HxAPV6J79vvouxKrWg2XV6ShFtPLP+0gPdGq3x9R3+kJbmAm8w+FOdlWqAfJrLvpzMGNeDU14YGXiZ9bVzmIQbwrBA+c/F4tlK/DV07dsNExihqFoibnqDiVNTGombaU2dDup2gwKdL81ua8EIcGNExHe82kjF4zwfadHk3bQVvbfdAwxcDy4xBjs3L4raPLU3yenSzr/OEur1+jfOxnQSmEcMXKXgrAQ9U55gwjcOFKrgOxEdek/Sk1VfOjvS+nuM4eyEruFMfaZHzoQiuw4IqgGc45ohFH0UUyjYcuFxxDSU9lMCv8qdHKm+wnPRb0l9l5vXsCBDuhAGYD6ss+Ga+aDY6f/qXZuUCEUOH3QUNbbCUlviSz6+GiRnt1kA9N2Qachl+2yBfaqUqr8h7Z2gsx5LcIf5kYNsqJ0GavXTVyWh7PYiKX4bs354ZQLUwwa/cG++2+wNWP+HtBhVxMRNTdVhSm38AknZlD+PTAsWGu9GyLmhti2EnVwGybSD2Dxmhxk3IPCkhKAK+pl0eWYGZWG3tJ9mZ7SowcXLWDFAk0lRJnKGFMTggrWjV8GYpw5bq23VmIqqDLgkNzuoog==
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

### 3.2、安装react-devtools获取更好的调试体验

1. 检出项目

在git上下载react-devtools文件到本地，下载地址： https://github.com/facebook/react-devtools

```shell
git clone https://github.com/facebook/react-devtools.git
```

2. 进入react-devtools文件夹，用npm安装依赖

```npm
npm install
```

3. 安装依赖成功后，打包一份扩展程序出来

```shell
npm run build:extension:chrome
```

执行成功后，会显示如下：

[react-devtools生成扩展程序成功](https://github.com/EmonCodingFrontEnd/frontend-tutorial/blob/master/tutorials/React/images/2018082101.png)

并且会在你的项目目录中生成一个新的文件夹`/react-devtools/shells/chrome/build/unpacked`

4. 打开chrome扩展程序`chrome://extensions/，加载已解压的扩展程序，选择第3步中生成的unpacked文件夹。这时就会添加一个新的扩展程序react-devtools，并在你的浏览器右上角有一个react标识，就表示成功了。

### 3.3、chrome插件

- EditThisCookie
- React Developer Tools 

- Redux DevTools（配合插件的一个扩展，Redux DevTools Extension）

## 4、安装WebStrom插件

- Styled Components

# 四、安装React官方脚手架

`create-react-app`为何物？ https://blog.csdn.net/qtfying/article/details/78665664

## 1、 安装`create-react-app`

全局安装，不需要每个webstorm安装一次。

```powershell
npm install -g create-react-app
```



## 2、创建react app项目

安装完成之后，生成一个新的项目，可以使用下面的命令：

```
create-react-app my-app
cd my-app
```

创建了`my-app`目录，这个时候，使用下面的命令就可以开始开发应用了。 

```
npm start
```

默认情况下，会在开发环境下启动一个服务器，监听在3000端口，它会主动给你打开浏览器的，可以立刻就看到这个app的效果。 

其他命令：

- 启动开发服务器

```shell
npm start
```

- 编译app到生产使用的静态文件

```shell
npm run build
```

- 启动测试运行

```
npm test
```



# 五、React

官网地址： https://reactjs.org/

## 1、package.json和package-lock.json的区别

- package.json

主要用来定义项目中需要依赖的包

- package-lock.json

在`npm install`时生成一份文件，用以记录当前状态下实际安装的各个npm package的具体来源和版本号。

## 2、React生命周期函数

生命周期函数指在某一个时刻组件会自动调用执行的函数。

- Initialization
  - setup props and state
- Mounting
  1. componentWillMount
  2. render
  3. componentDidMount
- Updation
  - props
    1. componentWillReceiveProps
    2. shouldComponentUpdate(nextProps, nextState)
    3. componentWillUpdate
    4. render
    5. componentDidUpdate
  - states
    1. shouldComponentUpdate(nextProps, nextState)
    2. componentWillUpdate
    3. render
    4. componentDidUpdate
- Unmounting
  - componentWillUnmount

## 9、其他

IconFont： http://www.iconfont.cn/

Reset CSS：调整浏览器的默认表现

https://meyerweb.com/eric/tools/css/reset/

# 七、ThinkJS

## 1、安装ThinkJS命令

```shell
npm install -g think-cli
```

安装完成后，系统中会有`thinkjs`命令（可以通过thinkjs -V查看think-cli的版本号，此版本号非thinkjs的版本号）。

如果是从`2.x`升级，需要将之前的命令删除，然后重新安装。

**卸载旧版本命令**

```shell
npm uninstall -g thinkjs
```

## 2、创建项目

执行`thinkjs new [project_name]`来创建项目，如：

```shell
thinkjs new demo;
cd demo;
npm install;
npm start;
```







