# remote-transmission

几种远程传输文件的方法总结
1.fileZilla

下载地址：https://filezilla-project.org
1）打开fileZilla客户端，点击站点管理器
2）配置完成后点击连接
主机：主机名称
端口：8000
协议：SFTP
登录类型：正常
用户名：登陆服务器使用的用户名
密码：你的密码
3）可通过简单的拖拽实现文件上传和下载

2.虚拟机之间文件互传

限于线上机器
1）在你需要get文件的机器上先起服务（举例：可以使用这种方法 python -m SimpleHTTPServer 8081）端口被占用时可以创建一个新的端口 
2）起了端口服务之后就可以使用 机器Ip：端口号 文件路径 把文件从一台机器上传输到另外一台机器上，
nohup wget -O 本地文件路径 机器Ip：端口号／文件路径
即可实现文件传输
3）也可以在本地浏览器中输入http://机器Ip：端口号 直接下载对应文件到本地
4）最后在服务端Control + c关掉打开的端口

3.SecureCRT

上传文件：在shell终端仿真器中输入命令"rz",从弹出的对话框中选择本地磁盘上的文件，利用Zmodem上传到服务器当前路径下。
下载文件：在shell终端仿真器中输入命令"sz" 文件名",利用Zmodem将文件下载到本地某目录下。
通过"File Transfer"可以修改下载到本地的默认路径，设置默认目录：options-->session options-->file transfer.
