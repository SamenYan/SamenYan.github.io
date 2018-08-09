title: cmd命令行--使用grunt工具自动化管理开发项目
date: 2016-08-13
tags:
    - grunt
---

### 1. 首先确保已经全局安装Node环境。安装详情见[Node官网](http://nodejs.org)

### 2. 运行cmd,本地新建testgruntjs目录(例如)：
```bash
mkdir testgruntjs //创建名为testgruntjs的文件夹
cd testgruntjs //进入新创建目录下
npm install grunt-cli //运行npm,安装grunt
```
> 安装完成后，本地的testgruntjs文件夹中已添加node_modules.

### 3. 开始创建grunt项目
```bash
mkdir app //新建app项目原文件夹
cd app
cd.>index.html //新建index.html文件
mkdir js
cd js
cd.>index.js //新建index.js文件
cd..
cd.. //回到testgruntjs路径下
```

### 4.初始化grunt，生成package.json文件
```bash
npm init

name: <testgruntjs> //项目名
version: <1.0.0> //版本号
description: learn grunt //描述
entry point: <index.js> //入口文件；默认，用不到
test command:  //测试命令；留空
git repository: //仓库地址；留空
keywords: grunt,test //关键词；自己随意写
author: samen //作者
license: <ISC> //协议；默认

is this ok?<yes> yes
```
> package.json文件已创建好，可以在本地编辑器中查看

### 5.新增devDependencies项目
```bash
npm install grunt --save-dev
```
>初始化的devDependencies:
```bash
"devDependencies": {
   "grunt": "^1.0.1"
}
```

### 6.装插件：npm install '插件名' --save-dev 【卸载插件：npm uninstall '插件名' --save-dev】

```bash
npm install load-grunt-tasks --save-dev //告知用户当前的处理任务，如copy，clean...
npm install time-grunt --save-dev //计算每次grunt操作花费的时间
```

>安装完两个插件的devDependencies变化：s
```bash
"devDependencies": {
    "grunt": "^1.0.1",
    "load-grunt-tasks": "^3.5.2",
    "time-grunt": "^1.4.0"
}
```

### 7.配置Gruntfile.js文件。
>打开编辑器创建名为Gruntfile.js的文件，添加代码如下。其中app是源文件目录，dist是grunt插件处理后的目标文件目录。这里仅演示了文件拷贝、文件删除、js压缩、图片压缩的配置使用。

```bash
'use strict' //声明使用ES5

module.exports = function(grunt) {
    //引入工具插件
    require('load-grunt-tasks')(grunt);
    require('time-grunt')(grunt);

    //配置项目路径
    var config = {
        app: 'app',
        dist: 'dist'
    }

    //任务配置
    grunt.initConfig({
        config: config,

        copy: {
            dist: {
                files: {
                    '<%= config.dist %>/index.html': '<%= config.app %>/index.html',
                    '<%= config.dist %>/js/index.js': '<%= config.app %>/js/index.js'
                }
            }
        },

        clean: {
            dist: {
                src: '<%= config.dist %>/**/*',
                filter: 'isFile'
            }
        },

        uglify: {
            my_uglify: {
                files: {
                    '<%= config.dist %>/js/index.min.js': [
                        '<%= config.app %>/js/index.js',
                        '<%= config.app %>/js/indexsec.js'
                    ]
                }
            }
        },

        imagemin: {
            my_imagemin: {
                options: {
                    optimizationLevel: 3 //定义 PNG 图片优化水平
                },
                files: [{
                    expand: true,
                    cwd: 'app/images/', 
                    src: ['**/*.{png,jpg,jpeg}'], // 优化 imag es目录下所有 png/jpg/jpeg 图片
                    dest: 'dist/images/' // 优化后的图片保存位置，覆盖旧图片，并且不作提示
                }]
            }
        }
    });
}
```
### 8.继续装插件。[grunt插件库](http://www.gruntjs.net/plugins)【加星号的是官方插件，不加的是个人开发者贡献】
```bash
npm install grunt-contrib-copy --save-dev //拷贝插件
npm install grunt-contrib-clean --save-dev //清除插件
```

>安装完两个插件的devDependencies的再次变化：
```bash
"devDependencies": {
    "grunt": "^1.0.1",
    "grunt-contrib-clean": "^1.0.0",
    "grunt-contrib-copy": "^1.0.0",
    "load-grunt-tasks": "^3.5.2",
    "time-grunt": "^1.4.0"
}
```

### 9.然后就可以愉快地使用插件了。如下grunt命令：

```bash
grunt copy //拷贝命令
grunt clean //清除命令
```

### 10.整理几款常用到的grunt插件
```bash
* grunt-contrib-copy: 复制文件或目录

* grunt-contrib-clean: 删除文件或目录

* grunt-contrib-uglify: 压缩js文件（可实现多个文件的压缩及合并）

* grunt-contrib-cssmin：CSS文件压缩

* grunt-contrib-jshint: 用于javascript代码的检查（并会给出建议），可以避免出现一些低级语法问题 //sublime中可以安装jshint插件校验js

* grunt-contrib-imagemin：图片压缩 //建议安装0.3.0版本：npm install grunt-contrib-imagemin@0.3.0 --save-dev 

* grunt-contrib-watch: 监听文件的变化

* grunt-contrib-concat: 合并文件
``` 
