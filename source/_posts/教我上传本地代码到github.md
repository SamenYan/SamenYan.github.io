title: 教你上传本地代码到github
date: 2016-03-19
tags:
	- git
---
##### 第一步：建立git仓库 #####

cd到你的本地项目根目录下，执行git命令
    
    git init

##### 第二步：将项目的所有文件添加到仓库中 #####
    
    git add .

> 如果想添加某个特定的文件，只需把.换成特定的文件名即可

##### 第三步：将add的文件commit到仓库 #####

    git commit -m "注释语句"


##### 第四步：去github上创建自己的Repository，创建页面如下图所示： #####

> 创建成功后拿到仓库的https地址，如 https://github.com/SamenYan/test.git

##### 第五步：将本地的仓库关联到github上 #####

    git remote add origin https://github.com/SamenYan/test.git

> 后面的https链接地址换成你自己的仓库url地址

##### 第六步：上传github之前，要先pull一下，执行如下命令： #####

    git pull origin master

##### 第七步，上传代码到github远程仓库 #####
    
    git push -u origin master

>执行完后，如果没有异常，等待执行完就上传成功了，中间可能会让你输入Username和Password，你只要输入github的账号和密码就行了


**转载请标明出处： 
[http://blog.csdn.net/hanhailong726188/article/details/46738929 ](http://blog.csdn.net/hanhailong726188/article/details/46738929  "教你上传本地代码github") 
本文参考：【海龙的博客】**