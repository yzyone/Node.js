
# node安装后的设置(node_global和node_cache) - windows #

之前安装node后就进行了demo的测试和学习，从网上拉取包的有时候不知道放在什么地方了，c盘也有，当前项目目录也有，挺乱的。

使用npm安装模块分为本地安装和全局安装。

本地安装：`npm install express`    会安装到当前项目

全局安装：`npm install express -g`  会安装到指定的目录(node_global)

另外，如果没有设置全局目录node_global，那么全局安装的文件将会保存到 C:\Users\XXX\AppData\Roaming\npm (XXX是自己设置的计算机名字)

所以，安装好node后，要设置一下node_global和node_cache(node缓存文件夹)

1，在node安装目录创建node_global和node_cache文件夹

2，设置环境变量：

用户变量设置：将用户变量中 PATH 的值改成 D:\Program Files\nodejs\node_global，没有PATH，可以直接添加。

系统变量设置：添加变量 NODE_PATH  值为：D:\Program Files\nodejs\node_modules

3，打开cmd，执行

```
npm config set prefix "D:\Program Files\nodejs\node_global"   
npm config set cache "D:\Program Files\nodejs\node_cache"
```


4，执行`npm install express -g` 后，查看node_global 文件夹



5，有时候用npm拉取包可能会很慢，可以用淘宝npm镜像代替npm进行拉包，就像github和gitee

执行：`$ npm install -g cnpm --registry=https://registry.npm.taobao.org`

然后就可以用 `cnpm install express -g` 进行拉包了，和npm一样。

————————————————

版权声明：本文为CSDN博主「scorpio_meng」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。

原文链接：https://blog.csdn.net/scorpio_meng/article/details/83314675