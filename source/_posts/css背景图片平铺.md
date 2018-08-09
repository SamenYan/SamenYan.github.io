title: CSS背景图片平铺 —— 摆脱依赖图片尺寸
date: 2016-08-30
tags:
	- html
	- css
---

图片尺寸：1024*640px  

### 1. cover法:

```bash
    body{
        background-image: url(http://pic10.nipic.com/20101103/5063545_000227976000_2.jpg);
        backgroound-size: cover;
    }
```

演示截图：

|**pc端**|**phone端**|
|:------:|:---------:|
|![cover法pc端演示截图](/images/cover-pc.png) |![cover法phone端演示截图](/images/cover-phone.png)|

### 2. zindex法

```bash
html:
    <div class="bg">
    	<img src="http://pic10.nipic.com/20101103/5063545_000227976000_2.jpg" alt=""/>
    </div> 

css:
    .bg {
        position: fixed;
        z-index: -1;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
    }
    .bg > img {
        width: 100%;
        height: 100%;
    }
```

演示截图：

|**pc端**|**phone端**|
|:------:|:---------:|
|![zindex法pc端演示截图](/images/zindex-pc.png)|![zindex法phone端演示截图](/images/zindex-phone.png)|


> 通过比较可知，当图片的尺寸不足以平铺整个屏幕背景时，cover法phone端会出现无法铺满的现象，而zindex方法可以解决这一问题。[【stackoverflow详细解释】](http://stackoverflow.com/questions/1150163/stretch-and-scale-a-css-image-in-the-background-with-css-only/7372377#7372377)

**测试demo代码**

```bash
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>CSS背景图片平铺-demo</title>
	<style type="text/css">
	/*cover法*/
	body{
		background-image: url(http://pic10.nipic.com/20101103/5063545_000227976000_2.jpg);
		background-repeat: no-repeat;
		background-size: 100% 100%;
	}
	/*zindex法*/
	.bg{
		position: fixed;
		top: 0;
		left: 0;
		z-index: -1;
		width: 100%;
		height: 100%;
	}
	.bg > img{
		width: 100%;
		height:100%;
	}
	</style>
</head>
<body>
	<!-- <div class="bg">
		<img src="http://pic10.nipic.com/20101103/5063545_000227976000_2.jpg" />
	</div> -->
</body>
</html>
```