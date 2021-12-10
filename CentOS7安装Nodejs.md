# CentOS7安装Nodejs #

直接部署

## 首先安装wget ##

	yum install -y wget

如果已经安装了可以跳过该步

## 下载nodejs最新的bin包 ##

可以在下载页面https://nodejs.org/en/download/中找到下载地址。然后执行指令

	wget https://nodejs.org/dist/v9.3.0/node-v9.3.0-linux-x64.tar.xz

然后就是等着下载完毕。

另外你也可以在你喜欢的任意系统上下载最新的bin包，然后通过FTP上传到CentOS上。

## 解压包 ##

依次执行

    xz -d node-v9.3.0-linux-x64.tar.xz
    tar -xf node-v9.3.0-linux-x64.tar

## 部署bin文件 ##

先确认你nodejs的路径，我这里的路径为~/node-v9.3.0-linux-x64/bin。确认后依次执行

    ln -s ~/node-v9.3.0-linux-x64/bin/node /usr/bin/node
    ln -s ~/node-v9.3.0-linux-x64/bin/npm /usr/bin/npm
    ln -s ~/node-v9.3.0-linux-x64/bin/npm /usr/bin/npx

注意ln指令用于创建关联（类似与Windows的快捷方式）必须给全路径，否则可能关联错误。

测试

    node -v
    npm
    npx

作者：IT宝哥哥

链接：https://www.jianshu.com/p/657d58a149d0

来源：简书

著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。