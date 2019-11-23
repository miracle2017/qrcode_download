### 用法（How to Use It）
      
引入jq和jquery.qrcode.min.js（First include jq and it in your webpage with the usual script tag）

    <script src="jquery.min.js"></script>
    <script src="jquery.qrcode.min.js"></script>
      
创建一个存放二维码的dom（Then create a DOM element which gonna contains the generated qrcode image. Lets say
      a div）
      
     <div id="qrcode"></div>
      
生成二维码填入刚创建的dom中（Then you add the *qrcode* in this container by）
      
     jquery('#qrcode').qrcode("this plugin is great");
      
此外还可以为二维码设置高和宽（You can set the height and width of the generated qrcode:）
      
    jquery('#qrcode').qrcode({width: 64,height: 64,text: "size doesn't matter"});
