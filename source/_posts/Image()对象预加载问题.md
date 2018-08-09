title: Image()对象的预加载--JS无法获取图片的宽高问题
date: 2016-08-02 11:00:00
tags:
    - js
---

### JS中的Image()对象是在window.onload()加载完再执行加载的。

```bash
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>JS预加载Image()对象</title>
</head>
<body>
    <input type="button" name="" value="载入图片" onclick="addImg('https://www.baidu.com/img/logo.gif')" />
    <script type="text/javascript">
        var Img = new Image();
        function addImg(isrc){ 
            Img.onload = function(){
                alert("complete:" + Img.complete); //'complete'
                document.body.appendChild(Img);
                alert(Img.width);//174
            }

            Img.src = isrc;
            alert(Img.src); //'https://www.baidu.com/img/logo.gif'
            alert(Img.width); //0
        }
</script>
</body>
</html>
```

#### js代码流程：16 --> 24.25.26 -->18.19.20.21 
> 所以对应demo中，先执行了第20行代码，取到图片的width为0，然后第18行开始加载Image对象，完成后才能准确地取到图片的宽度；