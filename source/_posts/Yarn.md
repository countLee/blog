---
title: Yarn--快速、可靠、安全的依赖管理工具。
date: 2018-12-19 10:52:41
tags: yarn
categories: 工具
img: ./img/yarn.jpeg
---
Yarn 是 Facebook, Google, Exponent 和 Tilde 开发的一款新的 JavaScript 包管理工具。就像我们可以从官方文档了解那样，它的目的是解决这些团队使用 npm 面临的少数问题，即：
```bash
1.安装的时候无法保证速度/一致性
2.安全问题，因为 npm 安装时允许运行代码
```
Yarn 同样是一个从 npm 注册源获取模块的新的 CLI 客户端。注册的方式不会有任何变化 —— 你同样可以正常获取与发布包。

## 一、 安装
	此次安装说明只针对macOS环境
### 1.1 Homebrew
你可以通过 [Homebrew](https://brew.sh/index_zh-cn) 包管理工具 安装 Yarn。 如果你还未安装 Node.js，Homebrew 会自动为你安装。
```bash
brew install yarn
```
如果你是 [nvm](https://github.com/creationix/nvm) 或类似工具，你应当避免安装 Node.js ，以便使用 nvm 版本的 Node.js 。
```bash
brew install yarn --without-node
```
### 1.2 MacPorts
你可以通过 [MacPorts](https://www.macports.org/) 安装 Yarn 。 如果你还未安装 Node.js ， MacPorts 会自动为你安装。 
```bash
sudo port install yarn
```
### 1.3 路径设置
如果未在 PATH 环境变量中找到 yarn，请按照以下步骤添加 yarn 到 PATH 环境变量中，使其可随处运行。

	注意：您的配置文件可能是 `.profile` 、 `.bash_profile` 、 `.bashrc` 、 `.zshrc` 等。
	
1. 将此项加入您的配置文件： `export PATH="$PATH:/opt/yarn-[version]/bin"` （路径可能根据您安装 Yarn 的位置而有差异）
2. 在终端中，执行登录并登出以使更改生效

为了可以全局访问 Yarn 的可执行文件，需要在您的终端中设置 `PATH` 环境变量。若要执行此操作，请添加 `export PATH="$PATH:`yarn global bin`"` 到您的配置文件中。

### 1.4 升级 Yarn
有新版时，Yarn会给你提示。如需升级 Yarn，仍然可以通过 Homebrew 来升级。
```bash
brew upgrade yarn
```
通过如下命令测试 Yarn 是否安装成功：
```bash
yarn --version
```

## 二、 使用方法
现在 Yarn 已经安装完毕，可以开始使用了。以下是最常用的命令：
**初始化一个新项目**
```bash
yarn init
```
**添加依赖包**
```bash
yarn add [package]
yarn add [package]@[version]
yarn add [package]@[tag]
```
**将依赖项添加到不同依赖项类别中**
分别添加到 devDependencies、peerDependencies 和 optionalDependencies 类别中：
```bash
yarn add [package] --dev
yarn add [package] --peer
yarn add [package] --optional
```
**升级依赖包**
```bash
yarn upgrade [package]
yarn upgrade [package]@[version]
yarn upgrade [package]@[tag]
```
**移除依赖包**
```bash
yarn remove [package]
```
**安装项目的全部依赖**
```bash
yarn
```
或者
```bash
yarn install
```