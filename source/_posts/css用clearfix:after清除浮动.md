title: css用clearfix:after清除浮动
date: 2016-08-10
tags: 
	- css
---

>为啥要整理clearfix情妇呢！尼玛，打个清浮出来个情妇。之前在某程时情妇css在官网拿过来直接用，也没考虑里面的每条代码是什么实现原理！结果，出来混总是要还的！去某评面试时被问到clearfix里面的具体css代码时有点小小的懵逼，虽然能答出来几个，但是不确定的感觉很不爽。明明感觉会的知识点还掌握不了多尴尬。所以这件事教会我，学习要注重细节，眼高手低迟早会暴露。所以C君们，做个心细的Coder吧！

#### 1.为什么要清除浮动？

>被浮动元素会脱离文档流，造成父元素高度为0的诡异现象；由以下demo可见：

*未清除浮动:*
!["未清除浮动样例图片"](/images/no_clearfix.png)

*已清除浮动:*
!["已清除浮动样例图片"](/images/has_clearfix.png)

#### 2.推荐使用伪类清浮：不会改变html结构，用法简单，只需要在被浮动元素的父元素加上clearfix类即可。如下代码所示：

html:
```bash
<div class="parent clearfix">
    <div class="floated"></div>
</div>
```
css:
```bash
.clearfix:after {
    content: '.'; //内容为“.”就是一个英文的句号而已。也可以不写。
    display: block; //转化为块级元素
    clear: both; //清除左右两边浮动
    line-height: 0;
    height: 0;
    visibility: hidden; //可见度设为隐藏
}
.clearfix{
    zoom:1;//兼容IE6、IE7，因为它俩不支持:after伪类,还好IE8以上是支持的
}
```


