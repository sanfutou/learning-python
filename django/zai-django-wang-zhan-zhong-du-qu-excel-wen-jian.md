# [django Excel文件预览](http://www.cnblogs.com/xucaifu/p/3727330.html)

      目前文档的在线预览方式大致有以下几种:

* 服务器先转换为PDF，再转换为SWF，最后通过网页加载Flash预览
* Office文档直接转换为SWF，通过网页加载Flash预览
* office转Html、pdf转图片在线预览文件Html文件
* 第三方ActiveX浏览器控件
* 微软的Office Web Apps
* 第三方成熟的服务
* 在浏览器中直接打开

    基于服务器、用户环境的考虑以及实现的复杂程度，这里选择使用office转html的方式来实现。Excel文件的读取使用python 开源库 xlrd 0.9.3。

   基本思路：

1. 打开指定文档
2. 读取指定sheet，默认为第一个
3. 处理合并单元格
4. 读取所有单元格，并生成html的table内容标签
5. 利用css和js调整table元素格式



  使用xlrd读取Excel文档遇到的问题：

* 用merged\_cells读取合并单元格时，列表为空，无法取得相应的数据

       解决办法：在打开文档时设置：formatting\_info 参数，之后成功获取相关格式信息。

      代码： wb = open\_workbook\(filepath,formatting\_info=True\)



 最后在网页中插入生成的table代码，并配合css和js显示Excel文档内容。显示效果与 idocv 一样，效率很高，如果数据量大可以加上分页处理功能，加上专业的css和js一定会使Excel文档的展现接近完美。



代码地址：https://github.com/XYFHY2004/Excel2Html.git



参考文档

http://www.officeweb365.com/officetoview.html

http://www.cppblog.com/snowzjy/articles/32056.html

http://www.cnblogs.com/flashlm/archive/2010/11/22/document-preview-online.html

http://www.cnblogs.com/flashlm/archive/2010/11/27/1889426.html

http://www.idocv.com

还没有试验，从网上找的。

