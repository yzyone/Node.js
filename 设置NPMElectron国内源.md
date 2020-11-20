# 设置NPM/Electron国内源 #
 

## Yarn设置国内镜像 ##

    yarn config set registry https://mirrors.huaweicloud.com/repository/npm/
    yarn config set disturl https://mirrors.huaweicloud.com/nodejs/
    yarn config set electron_mirror https://mirrors.huaweicloud.com/electron/
 
淘宝镜像

    yarn config set registry https://registry.npm.taobao.org
    yarn config set disturl https://npm.taobao.org/dist
    yarn config set electron_mirror https://npm.taobao.org/mirrors/electron/

注意：华为的镜像比较坑，貌似有些最新的镜像是没有的，先尝试了一下，踩坑后果断弃用，建议用淘宝的，后三条是设置淘宝国内镜像源的命令，开发Electron的时候，设置了一下Electron，这个最好还是用淘宝的哈，不然electron可能安装不上。

 

## NPM设置国内镜像 ##

    npm config set registry https://mirrors.huaweicloud.com/repository/npm/
    npm config set disturl https://mirrors.huaweicloud.com/nodejs/
    npm config set electron_mirror https://mirrors.huaweicloud.com/electron/

淘宝镜像

    npm config set registry https://registry.npm.taobao.org
    npm config set disturl https://npm.taobao.org/dist
    npm config set electron_mirror https://npm.taobao.org/mirrors/electron/

注意：华为的镜像比较坑，貌似有些最新的镜像是没有的，先尝试了一下，踩坑后果断弃用，建议用淘宝的，后三条是设置淘宝国内镜像源的命令，开发Electron的时候，设置了一下Electron，这个最好还是用淘宝的哈，不然electron可能安装不上。