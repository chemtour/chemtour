# 介绍

本



<div id="qrcode" style="position: relative;"></div>
<script type="text/javascript" src="assets/uqrcode.js"></script>
<script>
    // 引入uQRCode
    var UQRCode = window.UQRCode;
    // 获取uQRCode实例
    var qr = new UQRCode();
    // 设置二维码内容
    qr.data = "https://uqrcode.cn/doc";
    // 设置二维码大小，必须与canvas设置的宽高一致
    qr.size = 200;
    // 设置二维码前景图，可以是路径
    qr.foregroundImageSrc = 'src/images/aihg-chemtour-cover.png';
    // 调用制作二维码方法
    qr.make();

    var drawModules = qr.getDrawModules();
    // 遍历drawModules创建dom元素
    var qrHtml = '';
    for (var i = 0; i < drawModules.length; i++) {
        var drawModule = drawModules[i];
        switch (drawModule.type) {
        case 'tile':
            /* 绘制小块 */
            qrHtml += `<div style="position: absolute;left: ${drawModule.x}px;top: ${drawModule.y}px;width: ${drawModule.width}px;height: ${drawModule.height}px;background: ${drawModule.color};"></div>`;
            break;
        case 'image':
            /* 绘制图像 */
            qrHtml += `<img style="position: absolute;left: ${drawModule.x}px;top: ${drawModule.y}px;width: ${drawModule.width}px;height: ${drawModule.height}px;" src="${drawModule.imageSrc}" />`;
            break;
        }
    }
    document.getElementById('qrcode').innerHTML = qrHtml;
</script>


