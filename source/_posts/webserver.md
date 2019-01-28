---
title: Linux上新增web服务配置
date: 2019-01-28 11:06:18
tags:
  - server
  - Linux
comments: true
categories: linux
---
在做web开发的时候，经常会遇到部署静态资源到Linux服务器上。对于不是经常使用Linux系统的人可能有点陌生。下面把在Linux上新增一个web服务的配置过程记录下来，以备不时之需。以下展示的为手动配置基础版本。
## 前置条件
我们假设服务器上所有环境已经配置好：
- 文件上传Ftp服务
- Nginx服务
- 静态资源存放根目录：`/export/servers/source`
- Nginx根目录：`/export/servers/nginx`

## 一、新增静态资源目录
在静态资源根目录`/export/servers/source`下新建项目文件夹目录：`TestProject/dist/`
## 二、上传静态资源
利用FTP工具（如FileZilla）或者其他方式，把本地打包好的静态资源（包括html,js,css,图片等）上传到`/export/servers/source/TestProject/dist/`目录
## 三、配置Nginx
`cd /export/servers/nginx/conf/domains/`进入到Nginx的配置目录，打开对应网站域名的配置文件如：`static.yourdomain.com.conf`，添加如下所示的配置项：
```js
server  {
  ...#其他配置代码
   location /testproject/dist/ {
       alias  /export/servers/source/TestProject/dist/;
    }
}
```
保存当前配置文件并退出。
`cd /export/servers/nginx/sbin/`进入到nginx程序目录，执行命令：`./nginx -t`验证配置文件是否正确。如果错误按照提示进行修改。如果正确，执行命令：`./nginx -s reload`重启Nginx服务。
## 四、访问静态资源
绑定相关host,打开浏览器，输入`static.yourdomain.com/TestProject/dist/yoursource.js`访问对应的静态资源是否加载成功。如果加载成功，则说明静态资源服务配置成功。
