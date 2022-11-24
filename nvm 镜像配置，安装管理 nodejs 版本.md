# nvm 镜像配置，安装管理 nodejs 版本

众所周知 Windows 的node版本最方便的版本管理工具就是nvm，但是一般nvm有一个缺点就是下载特别的慢。

很多时候我们辛辛苦苦安装了nvm，然后辛辛苦苦等了很久的安装，结果还是安装失败。

## 1. nvm 镜像的配置 ##

自己踩过的坑，给大家分享下，如何配置 nvm 的镜像？请参考下边的操作

1.在 nvm 的安装路径下，找到 settings.txt，在后面加上这两行

```
node_mirror: http://npmmirror.com/mirrors/node/
npm_mirror: http://npmmirror.com/mirrors/npm/
```

如何找到nvm的安装路径？在搜索栏输入nvm ，然后右击“查看文件地址”，找到nvm的安装路径，这样你就能够找到 settings.txt 文件了

2.前面设置的其实是安装 npm 的镜像，而现在是用 npm 去安装 package，所以得设置让 npm 知道去哪获取 package:

```
npm config set registry http://registry.npmmirror.com
```

P.S.: mac 和 linux 版 nvm 就没有 node_mirror & npm_mirror 命令 ，设置下载 node 镜像地址的方式是

```
export NVM_NODEJS_ORG_MIRROR=https://nodejs.org/dist
```

大家在网上看到这种方式的时候，就要看看是不是符合自己的操作系统。然后请在 = 后边更改成下边的内容

```
http://npmmirror.com/mirrors/node
```

## 2. nvm 的使用 ##

```
nvm list //查看nvm下的node版本
nvm install 10.16.2 // 安装nodejs 10.16.2 版本
nvm use 10.16.2 // 使用nodejs 10.16.2的版本
nvm uninstall 10.16.2 //卸载 nodejs 10.16.2 版本
nvm -v // 查看nvm 相应的版本
```


希望这些能够帮助到大家！

**注意：**

原淘宝npm域名即将停止解析，请切换至新域名 npmmirror.com

http://npm.taobao.org和 http://registry.npm.taobao.org 将在 2022.06.30 号正式下线和停止 DNS 解析。

新域名为 npmmirror.com, 相关服务域名切换规则请参考：

```
http://npm.taobao.org => http://npmmirror.com
http://registry.npm.taobao.org => http://registry.npmmirror.com
```

————————————————

版权声明：本文为CSDN博主「KeivnLai」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。

原文链接：https://blog.csdn.net/qq_41409353/article/details/109553940