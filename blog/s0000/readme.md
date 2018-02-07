# 安装 NVM

## 什么是 nvm ？

nvm 是 Node Version Manager 的缩写，即 node 的版本管理工具，使用 nvm 可以无痛切换当前 node 版本。

## 下载

nvm-linux 的 github 地址

``` text
https://github.com/creationix/nvm
```

nvm-windows 的 github 地址

``` text
https://github.com/coreybutler/nvm-windows
```

nvm-windows 的下载地址

``` text
https://github.com/coreybutler/nvm-windows/releases
```

## 安装

### linux 系统下

``` shell
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.1/install.sh | bash
```

或

``` shell
wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.33.1/install.sh | bash
```

如果是远程连接主机的话，安装完成后需要重连，否则可能提示找不到 nvm 。

如果没有安装 git 的话，先安装 git

Ubuntu

``` shell
sudo apt-get install git
```

Centos

``` shell
sudo yum install git
```

### windows 系统下

从 nvm-window 下载地址中，选择最近版本并下载，解压后直接安装即可。安装完成后，需要重新启动 cmd 或者 powershell 。

## 常用命令

帮助信息

``` shell
nvm
```

安装指定版本的 node

``` shell
nvm install v9.0.0
nvm install 9
nvm install latest    # 安装最新的稳定版本
```

全局切换到指定版本的 node

``` shell
nvm use v8.9.0
```

查看当前系统已经安装的所有版本

``` shell
nvm list
或
nvm ls
```

### 注意

无论是 node 还是 nvm ，安装目录的路径中，都不要存在中文或空格，否则会报错。
