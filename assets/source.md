了解了源码的文件目录，本节我们学习两种调试源码的方式，一种是官方方式，一种是为本书读者定制的方式。

## 推荐方式

官方方式主要是为**想为 React 贡献代码的人**准备的，整体步骤比较繁琐。对于以“学习源码”为目的的读者，推荐的调试方式：[仓库地址](https://github.com/BetaSu/react18-demo)

这种方式有如下特点：

1. 调试信息清晰，`React`内的关键步骤都以**日志**的形式打印在控制台，并根据调用阶段不同会有不同颜色区分

2. 方便调试源码，采用`Vite`构建，对源码的修改会热更新

3. 丰富的示例，对多种场景提供示例

## 官方方式

构建`React`项目最常见的方式是使用`create-react-app`（后文简称`CRA`），但是`facebook/react`项目`main`分支的代码和我们使用`CRA`创建的项目`node_modules`下的`react`项目代码还是有些区别。

因为`React`的新代码都是直接提交到`main`分支，而`CRA`内的`React`使用的是稳定版的包。所以，为了调试最新的`React`代码，需遵循以下步骤：

1. 从`facebook/react`项目`main`分支拉取最新源码

2. 基于最新源码构建`react`、`scheduler`、`react-dom`三个包

3. 通过`CRA`创建测试项目，并使用步骤 2 创建的包作为项目依赖的包

### 拉取源码

拉取`facebook/react`代码：

```sh
# 拉取代码
git clone https://github.com/facebook/react.git

# 如果拉取速度很慢，可以考虑如下2个方案：

# 1. 使用cnpm代理
git clone https://github.com.cnpmjs.org/facebook/react

# 2. 使用码云的镜像（一天会与react同步一次）
git clone https://gitee.com/mirrors/react.git

```

安装依赖

```sh
# 切入到react源码所在文件夹
cd react

# 安装依赖
yarn
```

打包`react`、`scheduler`、`react-dom`三个包为 dev 环境可以使用的`cjs`包。

> 我们的步骤只包含具体做法，对每一步更详细的介绍可以参考`React`文档[源码贡献章节](https://zh-hans.reactjs.org/docs/how-to-contribute.html#development-workflow)

```sh

# 执行打包命令
yarn build react/index,react/jsx,react-dom/index,scheduler --type=NODE

```

现在源码目录`build/node_modules`下会生成最新代码的包。我们为`react`、`react-dom`创建`yarn link`。

> 通过`yarn link`可以改变项目中依赖包的目录指向

```sh
cd build/node_modules/react
# 声明react指向
yarn link
cd build/node_modules/react-dom
# 声明react-dom指向
yarn link
```

### 创建项目

接下来我们通过`CRA`在其他地方创建新项目。这里我们随意起名，比如“a-react-demo”。

```sh
npx CRA a-react-demo
```

在新项目中，将`react`与`react-dom`2 个包指向`facebook/react`下我们刚才生成的包。

```sh
# 将项目内的react react-dom指向之前声明的包
yarn link react react-dom
```

现在试试在`react/build/node_modules/react-dom/cjs/react-dom.development.js`中随意打印些东西。

在`a-react-demo`项目下执行`yarn start`。现在浏览器控制台已经可以打印出我们输入的内容了。

通过以上方法，我们项目中的`React`就和`main`分支代码一致了。
