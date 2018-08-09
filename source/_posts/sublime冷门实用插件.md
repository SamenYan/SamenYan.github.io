title: sublime 冷门实用插件
date: 2016-08-20
tags:
	- st
---

论sublime插件，我只服[豪情大神](https://github.com/jikeytang/sublime-text)

### 1. HTML-CSS-JS-JSON 自动格式化插件

* 在Sublime Text中，按下Ctrl+Shift+P调出命令面板;

* 输入install 调出 Install Package 选项并回车;

* 输入pretty，并在列表中选择HTML-CSS-JS Prettify后回车即可安装

**使用方法：打开一个HTML-CSS-JS-JSON中的任何一种文件，按下ctrl+Shirt+H（记得取消搜狗默认更换皮肤快捷键,避免冲突）;**

>特别提醒：该插件需要Nodejs的支持。如下图所示，找到相应系统配置本地node文件目录即可

![nodejs配置](/images/node-config.png);

### 2.JSHint Gutter JS校验插件

* 在Sublime Text中，按下Ctrl+Shift+P调出命令面板;

* 输入install 调出 Install Package 选项并回车;

* 输入jshint，并在列表中选择JSHint Gutter后回车即可安装

**使用指南：**

JSHint插件不会自动执行，调出步骤：

> 1.安装完成后，进入一个本地js文件，移动到JSHint-->Set Plugin Options;

![jshint截图1](images/jshint-01.png)

> 2.配置JShint文件。"lint_on_edit"改为true默认启用插件，也可以使用快捷键"ctrl+alt+j"启用插件（右击JSHint-->Set Keyboard Shortcuts自定义设置）

![jshint截图2](images/jshint-02.png)

> 3.demo演示，插件使用

![jshint截图3](images/jshint-03.png)

> 4.提示错误修改后

![jshint截图4](images/jshint-04.png)

> 5.clear后没有报错了

![jshint截图5](images/jshint-05.png)

>特别提醒：该插件同样需要node的支持aa。

### 3.Terminal 控制台呼出插件

* 使用快捷键 ctrl+shift+T 呼出当前文件路径的控制台

* 用node，Grunt等等时调出控制台不要太6

![terminal截图1](images/terminal-01.png)

### 4. CSS Format css各种格式化

* 安装过程同上，安装完成后在编辑器中打开**css文件**（其他文件format选项没卵用）
* 右击出现CSS Format选项，里面几乎可以满足你所有想要的css格式化；

![CSS Format截图1](images/css-format.png)