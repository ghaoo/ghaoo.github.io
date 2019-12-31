---
date: 2019-09-24
time: 14:12:46
title: npm 常用命令
categories:
- js
tags:
- js
- npm
---

[toc]

- `npm init` 在此目录生成package.json文件，可以添加 `-y` | `--yes` 参数则默认所有配置为默认yes

- `npm install <package> -g` 全局安装

- `npm install --production` 安装`dependencies`，不包含`devDependencies`

- `npm install <package>` 默认使用–save 参数，如果不想保存到`package.json`中，可以添加`--no-save`参数；还可以指定`–save-dev` 或 `-g`参数

- `npm uninstall <package>` 卸载依赖包， 默认使用`–save`参数，即从`package.json`中移除

- `npm ls [-g][--depth=0]` 查看当前目录或全局的依赖包，可指定层级为`0`

- `npm outdated` 查看当前过期依赖，其中`current`显示当前安装版本，`latest`显示依赖包的最新版本，`wanted`显示我们可以升级到可以不破坏当前代码的版本

- `npm root -g` 查看全局安装地址

- `npm update <package>` 升级依赖包版本

- `npm ll[la][--depth=0]` 查看依赖包信息

- `npm list <package>`查看依赖的当前版本

- `npm search <string>` 查找包含该字符串的依赖包

- `npm view <package> [field][--json]`列出依赖信息，包括历史版本，可以指定field来查看某个具体信息，比如（versions) 可以添加`–json`参数输出全部结果

- `npm home <package>` 在浏览器端查看项目（项目主页）

- `npm repo <package>` 浏览器端打开项目地址（GitHub）

- `npm docs <packge>` 查看项目文档

- `npm bugs <packge>` 查看项目bug

- `npm prune` 移除当前不在`package.json`中但是存在`node_modules`中的依赖

- `npm link` 不使用`npm install` 而连接某个依赖包，通常用作开发本地依赖包
