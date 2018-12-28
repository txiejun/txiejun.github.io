---
title: linux命令笔记
date: 2018-12-28 11:27:40
tags:
  - linux
  - mac
comments: true
categories: linux
---
Shell命令是使用Linux或者Mac系统的人经常接触的一种脚本语言。相关教程可以[看这里](http://www.runoob.com/linux/linux-shell.html)
## Linux chown命令和chmod命令
网上一张很形象的对比图：
![对比](/images/linuxcmd/chownVschmod.jpg)
- chown：Linux中用来改变某个文件的属主的命令，如漫画中所示，将某个“资源”（门）的访问权限给予别人。
- chmod：Linux中用来改变某个文件的访问模式的命令，如漫画中所示，chmod 777 会将“大门”敞开，谁都可以进出了。

### 1、chown命令
Linux/Unix 是多人多工操作系统，所有的文件皆有拥有者。利用 chown 将指定文件的拥有者改为指定的用户或组，用户可以是用户名或者用户ID；组可以是组名或者组ID；文件是以空格分开的要改变权限的文件列表，支持通配符。
使用权限：root
语法
```js
chown [-cfhvR] [--help] [--version] user[:group] file...
```
参数：
- user : 新的文件拥有者的使用者 ID
- group : 新的文件拥有者的使用者组(group)
- -c : 显示更改的部分的信息
- -f : 忽略错误信息
- -h :修复符号链接
- -v : 显示详细的处理信息
- -R : 处理指定目录以及其子目录下的所有文件
- --help : 显示辅助说明
- --version : 显示版本

实例：
将文件 file1.txt 的拥有者设为 users 群体的使用者 runoob :
```js
chown runoob:users file1.txt
```
将目前目录下的所有文件与子目录的拥有者皆设为 users 群体的使用者 lamport :
```js
chown -R lamport:users *
```
一般需要加上sudo命令来执行。

### 2、chmod命令
Linux/Unix 的文件调用权限分为三级 : 文件拥有者、群组、其他。利用 chmod 可以藉以控制文件如何被他人所调用。
使用权限：所有使用者
语法
```js
chmod [-cfvR] [--help] [--version] mode file...
```
参数：
- mode : 权限设定字串，格式如下 :
```js
[ugoa...][[+-=][rwxX]...][,...]
```
其中：
> 	u 表示该文件的拥有者，g 表示与该文件的拥有者属于同一个群体(group)者，o 表示其他以外的人，a 表示这三者皆是。
> 	+ 表示增加权限、- 表示取消权限、= 表示唯一设定权限。
> 	r 表示可读取，w 表示可写入，x 表示可执行，X 表示只有当该文件是个子目录或者该文件已经被设定过为可执行。

- -c : 显示更改的部分的信息
- -f : 忽略错误信息
- -h :修复符号链接
- -v : 显示详细的处理信息
- -R : 处理指定目录以及其子目录下的所有文件
- --help : 显示辅助说明
- --version : 显示版本

实例：
将文件 file1.txt 设为所有人皆可读取 :
```js
chmod ugo+r file1.txt
```
或者
```js
chmod a+r file1.txt
```
将目前目录下的所有文件与子目录皆设为任何人可读取 :
```js
chmod -R a+r *
```
或者
```js
chmod 777 file
```

#### 注意：
chmod也可以用数字来表示权限，语法为：
```js
chmod abc file
```
其中a,b,c各为一个数字，分别表示User、Group、及Other的权限。
r=4，w=2，x=1
若要rwx属性则4+2+1=7；
若要rw-属性则4+2=6；
若要r-x属性则4+1=5。

```js
chmod ug=rwx,o=x file
```
和
```js
chmod 771 file
```
效果相同

参考：
[详细记录 mac 系统下使用 chmod 命令修改文件权限](http://yifeng.studio/2017/10/18/mac-terminals-chmod-command/)