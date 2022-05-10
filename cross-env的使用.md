# cross-env的使用 #

cross-env怎么使用，作用是什么，根据官网的解释它是这样子的

当您使用这样设置环境变量时，大多数 Windows 命令提示符都会阻塞 NODE_ENV=production。（例外是Bash on Windows，它使用本机 Bash。）同样，windows 和 POSIX 命令使用环境变量的方式也有所不同。在 POSIX 中，您使用：$ENV_VAR ，在 Windows 上，您使用%ENV_VAR%

cross-env使您可以拥有一个命令，而无需担心为平台正确设置或使用环境变量。就像在 POSIX 系统上运行时一样设置它，并且cross-env会正确设置它。

简而言之个人的理解是：

我们通过cross-env设置环境变量，可以很好的是适配多个平台，无语根据平台来设置相对应的变量

官网地址：

	https://www.npmjs.com/package/cross-env

安装：

	npm install --save-dev cross-env

官网的案例：

```
{
  "scripts": {
    "build": "cross-env NODE_ENV=production webpack --config build/webpack.config.js"
  }
}
```

衍生

有没有考虑过，可以给NODE环境设置一个变量，通过process.env.xxxxx来获取，我们根据相对应的变量进行不同的配置。

```
{
  "scripts": {
    "dev:oneProject": "cross-env PROJECT_NAME=oneProject vue-cli-service serve"
  }
}
```

这个段代码我们设置了一个PROJECT_NAME的变量，通过process.env.PROJECT_NAME来获取到变量的值oneProject 。
可能有人问，这样子的设置有何作用，可以看下我的《[vue-cli分模块打包，根据每个模块独立打包并且独立运行](https://www.jianshu.com/p/475a76542582)
》这篇文章就会一目了然了。

在这里感谢大家的感觉，我的文章对你们有帮助的话，希望点赞并关注。你们的支持是我坚持不懈的动力

作者：柯柯的呵呵哒

链接：https://www.jianshu.com/p/0771ef611007

来源：简书

著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。