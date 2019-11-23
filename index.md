<!DOCTYPE html>
<html>
<head>
    <title>Demo page(生成图片并生成下载图片,实现下载功能)</title>
    <meta charset="utf-8">
</head>
<body>
<h1>
    文字生成二维码及生成可下载的图片
</h1>

<div id="output"></div>
<p>上面的码是使用canvas标签, 下面的是img标签</p>

<style>
    * {
        text-align: center;
    }
    a {
        font-size: 30px;
        display: block;
    }
</style>
<script src="../src/jquery.min.js"></script>
<script type="text/javascript" src="../src/jquery.qrcode.min.js"></script>
<script>
    jQuery(function () {
        //http://www.ylnysm.com可以自定义任意你要的链接或者文字
        jQuery('#output').qrcode("http://www.ylnysm.com");
    });
    window.onload = function () {
        let drawing = document.getElementsByTagName('canvas')[0];
        //确定浏览器支持<canvas>元素
        if (drawing.getContext) {
            let context = drawing.getContext('2d');
            console.log(context);
            //取得图像的数据 URI
            let imgURI = drawing.toDataURL("image/png");
            //显示图像
            let image = document.createElement("img");
            image.src = imgURI;
            document.body.appendChild(image);
            //显示下载链接
            let a = document.createElement("a");
            a.href = imgURI;
            //设置下载链接的文字提示
            a.innerText = 'download qrcode';
            //设置下载的文件名
            a.download = 'test.png';
            document.body.appendChild(a);
        }
    }
</script>
</body>
</html>
