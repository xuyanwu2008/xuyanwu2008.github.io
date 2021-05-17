---
title: FTP常见命令详解 
tags: ftp,Linux
renderNumberedHeading: true
grammar_cjkRuby: true
---


在window下按window + r可打开DOS命令窗口，然后就可以输入FTP命令了。

1. 登录FTP服务器
方法一：直接输入ftp加ip地址ftp 192.168.10.xxx
方法二：直接输入ftp，进入ftp服务后输入open加ip地址open 192.168.10.xxx
当连接成功后会让你进行身份验证，在输入密码时屏幕上没有任何显示，不用管，直接输完密码敲回车键即可。

2. 查看FTP服务器上的文件
（一般情况下用户都会被限制目录的访问权限，只可在当前目录下进行操作）
dir：显示服务器目录和文件列表
ls：显示服务器简易的文件列表
cd：进入服务器指定的目录

dir命令可以使用通配符“”和“?”，比如，显示当前目录中所有扩展名为jpg的文件，可使用命令 dir .jpg。

cd命令中必须带目录名。比如 cd main 表示进入当前目录下的main子目录

3. 下载文件
上传和下载文件时应该使用正确的传输类型，FTP的传输类型分为ASCII码方式和二进制方式两种，对.txt、.htm等文件应采用ASCII码方式传输，对.exe或图片、视频、音频等文件应采用二进制方式传输。在默认情况下，FTP为ASCII码传输方式。
type：查看当前的传输方式
ascii：设定传输方式为ASCII码方式
binary：设定传输方式为二进制方式
（以上命令都不带参数）
get：下载指定文件get filename [newname](filename为下载的FTP服务器上的文件名，newname为保存在本都计算机上时使用的名字，如果不指定newname，文件将以原名保存。

get命令下载的文件将保存在本地计算机的工作目录下。该目录是启动FTP时在盘符C:后显示的目录。如果想修改本地计算机的工作目录，可以使用 lcd 命令。比如：lcd d:\ 表示将工作目录设定为D盘的根目录。

mget：下载多个文件mget filename [filename ....]（mget命令支持通配符“”和“?”，比如：mget .mp3 表示下载FTP服务器当前目录下的所有扩展名为mp3的文件。）

4. 上传文件
put：上传指定文件put filename [newname]
send：上传指定文件send filename [newname]
（filename为上传的本地文件名，newname为上传至FTP服务器上时使用的名字，如果不指定newname，文件将以原名上传。）

上传文件前，应该根据文件的类型设置传输方式，本机的工作目录也应该设置为上传文件所在的目录。

这里的send和put方法用法都基本相同，但是上传速度send却要比put快很多，有兴趣的人可以去研究下。
5. 结束并退出FTP
close：结束与服务器的FTP会话
quit：结束与服务器的FTP会话并退出FTP环境
6. 其它FTP命令
pwd：查看FTP服务器上的当前工作目录
rename filename newfilename：重命名FTP服务器上的文件
deletefilename：删除FTP服务器上的文件
help[cmd]：显示FTP命令的帮助信息，cmd是命令名，如果不带参数，则显示所有FTP命令
————————————————
版权声明：本文为CSDN博主「luckycyong」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/qq_38526635/article/details/82147980