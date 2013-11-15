nodeJc
======

Compression with js/CSS request, and according to the request to generate a new merger compressed js/CSS files
用于压缩合并Jsp/php/html等页面中的js和css请求，同时根据压缩后的请求生成新的js或css文件，以减少页面的请求，可用于cdn

==========
在conf/conf.js中进行设置



var arg = require('../nodeJc').arg;

module.exports = {
    "rootDir":"/home/hale/workspace/prod/",     //需要合并压缩的项目的根目录
    "jcRootDir":"/home/hale/workspace/",        //js/css实际存放项目根目录
    "jcDir":arg.length>0 ? arg : ["/home/hale/workspace/prod/activity/test.html"],  //需要合并压缩的目录绝对路径（可以与根目录相同）
    "extension":[".jsp",".php",".html",".ejs"],      //需要解析的扩展名
    "blacklist":["DD_belatedPNG_0.0.8a.*.js"],                        //不需要合并压缩的名单，正规格式
    "jsReq":"http://nuomi.xnimg.cn/Jc/js/",                      //合并后js资源url
    "cssReq":"http://nuomi.xnimg.cn/Jc/css/",                      //合并后css资源url
    "jsDir":"/home/hale/workspace/Jc/js/",     //压缩合并后js目录
    "cssDir":"/home/hale/workspace/Jc/css/"     //压缩合并后css目录
}

========
nodeJc为应用主程序，运行中可以在node上自带参数用以设置需要合并压缩的目录，同时处理多个路径请将多个路径放入数组中
另页面上的Js/css文件的引入最好用绝对路径

=======
压缩js用的是uglify-js,css用的是clean-css

=======
例：
配置好cong.js后，直接运行node nodeJc
或
node nodeJc /home/....



