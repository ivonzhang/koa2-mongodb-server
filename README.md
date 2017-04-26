# koa2-mongodb-server
利用koa2+mongodb搭建一套简易的nodejs后台服务，用于为客户端提供数据请求的数据api接口

# 使用说明
- 安装NodeJs  
  koa2下，最好安装node7.0以上版本，不然会报错，因为低版本下Koa2部分ES7的语法会不支持
- 安装MongoDB数据库  
  可以参考官方文档：https://docs.mongodb.com/manual/installation/ ；OS X 系统下推荐使用Homebrew进行安装。
- 安装相关依赖  
   cd到项目根目录下，执行：npm install （淘宝镜像下：cnpm install）
- 终端开启nodejs服务  
  cd到项目根目录，执行：node app
- DHC测试接口  
  安装Chrome插件DHC，对相关接口进行测试，如：

    ![signup接口测试](http://upload-images.jianshu.io/upload_images/5307186-1efca5d7c8ddd2ff.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 项目目录结构说明
  
![项目目录结构](http://upload-images.jianshu.io/upload_images/5307186-d29cb13923ae11db.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 控制器：controllers/user.js  
  用于接收用户模块的接口请求，如注册、更新、删除、获取用于列表、搜索用户等相关请求，以下是注册请求的举例。主要是通过koa-router实现路由转发请求到该接口，然后使用封装的dbHelper对mongodb进行操作（当然这里我直接使用了mongose的api进行数据库的操作了，比较low）。

    ![用户注册接口的实现](http://upload-images.jianshu.io/upload_images/5307186-bd283eeebc2a704d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- model层：表结构的定义，model/user.js  
  mongoose的语法，先定义一个schema，再导出一个model。mongoose的文档可以参考：http://www.nodeclass.com/api/mongoose.html 。
  
![用户表结构](http://upload-images.jianshu.io/upload_images/5307186-a2f18ca07c580904.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- koa2的使用  
  还是贴一下文档吧：https://github.com/koajs/koa

- koa-router的使用  
  再贴文档：https://github.com/alexmingoia/koa-router 

# 使用RAP  
  使用淘宝的rap来记录设计项目的API接口：http://rapapi.org/org/index.do
  
  ![更新用户信息接口的设计](http://upload-images.jianshu.io/upload_images/5307186-a628a6d42d64f4bf.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)







