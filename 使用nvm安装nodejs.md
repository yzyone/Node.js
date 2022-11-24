# 使用nvm安装nodejs #

## 安装nvm ##

nvm是nodejs的版本管理工具，可以快速切换更新nodejs版本,windows系统使用nvm-windows。

curl下载：

	curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash

wget下载：

	wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash

检查环境变量的配置：

	cat ~/.bash_profile

如果出现以下内容则是配置好了，否则请加以下内容添加到.bash_profile文件中：

```
# This loads nvm
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh"
```

添加完后需要重启脚本：

	source ~/.bash_profile

使用zsh需要注意，每次打开新的终端窗口都会无法使用nvm命令，需要把.bash_profile添加到.zshrc文件中：

- 打开~/.zshrc文件 
- 找到# User configuration所在的行 
- 在下方添加source ~/.bash_profile 
- 保存退出后重新执行脚本source ~/.zshrc

验证是否安装完成：

	nvm --version
 

windows安装

打开nvm-windows库的releases，下载最新版的nvm-setup.zip。 安装时会需要选择两个安装目录，一个是nvm的目录，另一个是node的版本库目录，我这里分别用C:\nvm和C:\nvm\nodejs。 

安装完后打开C:\nvm\setting.txt添加以下内容，切换node和npm的下载镜像，国内会快很多：

    node_mirror: https://npmmirror.com/mirrors/node/
    npm_mirror: https://npmmirror.com/mirrors/npm/

检查是否安装完成：

	nvm version
 

## 安装nodejs ##

nvm安装完后就可以开始管理nodejs的版本了

```
# 最新的lts版本
nvm install --lts

# windows 需要准确的版本号才可以下载(v要不要都可以)
nvm install v10.16.3
```

安装完后需要切换node版本：

```
# macOS系统的use指令只是临时切换
nvm alias default v10.16.3

# windows在首次安装完后必须执行该命令，否则无法找到node命令，
nvm use v10.16.3
```

配置淘宝镜像：

```
npm config set registry https://registry.npmmirror.com/ --global 
npm config set disturl https://npmmirror.com/dist --global
```

验证是否安装完成：

    npm -v
    npx -v
    node -v
 

## nvm常用命令 ##

```
nvm install --lts # 下载最新的稳定版
nvm use <版本号> # 临时切换版本
nvm alias default <版本号> #永久切换版本（版本别名，default就是默认使用的版本）
nvm uninstall <版本号> # 删除指定版本
nvm ls # 查看本地所有版本
nvm ls-remote --lts # 查看线上所有稳定版 
```

windows：

```
nvm install <版本号> # 下载指定版本
nvm use <版本号> # 切换版本
nvm uninstall <版本号> # 删除指定版本
nvm list available # 查看线上所有版本
资源搜索网站大全 https://www.renrenfan.com.cn 广州VI设计公司https://www.houdianzi.com
```

node常用命令

```
npm init # 初始化node环境，-y可以快速初始化
npm i <package> # 下载指定库，看情况添加 -S或者-D，全局安装-g
npm uninstall <package> # 删除node包，删除全局-g
npm list --depth 0 # 查看当前目录下载的node包
npm list -g --depth 0 # 查看全局安装的node包
```