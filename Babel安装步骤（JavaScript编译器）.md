# Babel安装步骤（JavaScript编译器） #

首先需要安装node.js按照官网‘下一步’就行

1.`npm init`

初始化

2.安装依赖包

    npm install --save-dev @babel/core @babel/cli

如果说提示babel不是命令，可以全局安装npm install --global @babel/core @babel/cli

3.运行`babel src -d lib`

或者在package.json中配置scripts属性，添加一个属性build:“`babel src -d lib`”，运行`npm run build`

4.想要语法进行转换，得指定从哪种语法转哪种语法，所以需要安装语法转换器插件

    npm install --save-dev @babel/preset-env

5.配置babel

创建一个.babelrc的文件，写入

```
{
    "presets": ["@babel/preset-env"]
}
```

6.运行`npm run build` 或者`babel src -d lib`

7.转换后的语法就可以在服务器nodejs环境下使用

8.如果想要转换后的代码在服务器和浏览器都可以使用，需要安装babel插件@babel/plugin-transform-modules-umd

    npm install --save-dev @babel/plugin-transform-modules-umd

9.在.babelrc中添加"plugins": ["@babel/plugin-transform-modules-umd"] //在babel进行模块化转换的时候使用这个插件

10.运行`npm run build 或者babel src -d lib`

11.编译过后就可以在浏览器中或者服务器nodejs环境下使用编译过后的js

浏览器中：需要requirejs

服务器中：需要运行node **.js命令

————————————————

版权声明：本文为CSDN博主「罗恩-HAO」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。

原文链接：https://blog.csdn.net/qq_40958876/article/details/96289101