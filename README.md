# beauty_website_creator

## section

构建美女图片站，包含以下几个部分：

- 爬虫：从美女图片站点爬取图片
- 色情检测：通过色情监测去掉色情图片
- 水印：去掉原始水印，增加自己的水印
- wordpress批量上传：将最终图片批量上传到wordpress中

具体操作见代码：只是简单写一下脚本，了解其中过程，没有形成系统。

## record

1. haole_no_porn中的色情图像已全部去除，需要检测右下角的澳门银河赌场，更换为自己的水印，区域大小（160 * 35）	
2. 调整ycbcr，使用photo_classify分析剩余的照片，得到一个比较合适区间值，来区分清纯图片和性感图片（初步定为80 <= cb <= 120 and 133 <= cr <= 173）
3. 根据2中的取值，对每一张照片进行清纯和性感检测，清纯图片改名为1__原名，性感图片改名为2__原名
4. 通过邮件的方式批量发送文章（含feature photo）到wordpress，完成站点图片的更新
