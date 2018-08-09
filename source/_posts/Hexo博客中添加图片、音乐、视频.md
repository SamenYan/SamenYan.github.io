title: Hexo博客中添加图片、音频、视频
date: 2016-03-19 14:10:59
tags:
	- hexo
---

#### 插入外链图片

```bash
!["图片描述"](图片外链地址)
```
> 注：外链地址不需要加引号

#### 插入本地图片

```bash
!["图片描述"](图片本地地址)
```
> 在\hexo\source目录下新建images文件夹，插入上面的代码样式即可
> 建议先压缩本地图片：[图好快](http://www.tuhaokuai.com/)

#### 插入外链音频

```bash
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=330 height=86 src="http://music.163.com/outchain/player?type=2&id=247415&auto=0&height=66"></iframe> 
```
>插入音频文件一般是通过插入iframe或者flash。以网易云音乐为例，打开官网-->搜索《春分》-->点击生成外链-->复制HTML代码；此外可以自定义宽高和是否自动播放。如下截图：
!["插入音频文件截图01"](/images/insert-music-pic.png)
!["插入音频文件截图02"](/images/insert-music-pic-sec.png)
效果图：
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=330 height=86 src="http://music.163.com/outchain/player?type=2&id=247415&auto=0&height=66"></iframe>

#### 插入本地音频

```bash
<audio controls height="100" width="100">
  <source src="本地音频地址" type="audio/mpeg">
  <embed height="50" width="100" src="本地音频地址">
</audio>
```

#### 插入视频

```bash
<iframe src="http://open.iqiyi.com/developer/player_js/coopPlayerIndex.html?vid=ec65a777d2b7e13e97c866f25b2b6d6d&tvId=515639900&accessToken=2.f22860a2479ad60d8da7697274de9346&appKey=3955c3425820435e86d0f4cdfe56f5e7&appId=1368&height=100%&width=100%" frameborder="0" allowfullscreen="true" width="100%" height="100%"></iframe>
```

>插入视频文件同上，复制出上面类似外链Html代码即可。
