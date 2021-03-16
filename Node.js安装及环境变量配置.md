
# Node.js安装及环境变量配置（windows） #

个人记录，便于安装

1.下载安装（省略）

2.检查node、npm是否安装成功

    node -v
    npm -v

3.环境配置
进入node.js根目录，创建node_global和node_cache文件夹，输入cmd命令：

    npm config set prefix "D:\Program Files\nodejs\node_global"
    npm config set cache "D:\Program Files\nodejs\node_cache"

接下来设置环境变量

1.系统创建 NODE_PATH

    D:\Program Files\nodejs\node_modules

2.修改用户 path

    C:\Users\Karma\AppData\Roaming\npm 

修改为 

    D:\Program Files\nodejs\node_global

4.淘宝镜像安装（cnpm）


    npm install -g cnpm --registry=https://registry.npm.taobao.org

测试：

    cnpm install express -g

————————————————

版权声明：本文为CSDN博主「仲尼叔叔」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。

原文链接：https://blog.csdn.net/weixin_40826349/article/details/95355988