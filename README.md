# tlbb-server

#### 架设步骤
第一步
```
Xshell工具下
运行以下命令

yum install -y wget git vim && \
cd ~ && git clone https://gitee.com/QQ63732956/tlbb-server.git /opt
```
第二步
```
Xshell工具下
运行以下命令

cd /opt && chmod +x install.sh
sh install.sh
```
第三步
```
用WinSCP工具上传天龙八部服务端到home目录下
```
第四步
```
Xshell工具下
解包tlbb.tar.gz
命令如下

cd /home
tar xzvf tlbb.tar.gz
```
第五步
```
用WinSCP工具复制到本地修改
然后上传回原来位置替换

修改服务端配置文件
/home/tlbb/Server/Config

配置文件如下
LoginInfo.ini
ShareMemInfo.ini
ServerInfo.ini

修改LoginInfo.ini配置文件下
DBPassword 项为数据库密码

修改ShareMemInfo.ini配置文件下
DBPassword 项为数据库密码

修改ShareMemInfo.ini配置文件下
双机版修改
[Billing]项下的
IP0        修改为win机IP
Port0      修改为win机Billing端口
[Server0]项下的
IP0        修改为服务器IP
Port0      修改为游戏端口
[Server1]项下的
IP0        修改为服务器IP
Port0      修改为登陆端口

单Linux版修改
[Billing]项下的
IP0        修改为127.0.0.1
Port0      修改为Billing相同端口
[Server0]项下的
IP0        修改为服务器IP
Port0      修改为游戏端口
[Server1]项下的
IP0        修改为服务器IP
Port0      修改为登陆端口
```
第六步
```
Xshell工具下
启动服务端引擎
命令如下

cd /home/tlbb
./run.sh

停止服务端引擎
命令如下

cd /home/tlbb
./stop.sh
```
### 到此就可以登陆游戏了

### tlbb-server命令大全
```
解压命令：
cd /home
tar xzvf tlbb.tar.gz

打包命令
cd /home
tar zcvf yx.tgz tlbb

删除命令：
cd /home
rm -rf tlbb

启动命令：
cd /home/tlbb/
./run.sh

停止命令:
cd /home/tlbb/
./stop.sh

分布启动命令：
克隆SSH1
cd /home/tlbb/Server
./shm start
克隆SSH2
cd /home/tlbb/Server
./Login
克隆SSH3
cd /home/tlbb/Server
./World
克隆SSH4
cd /home/tlbb/Server
./Server

校对时间命令：
rm -rf /etc/localtime
ln -s /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

启动数据库命令：
service mysqld restart

永久关闭防火墙命令：
systemctl stop firewalld.service
systemctl disable firewalld.service

常看防火墙开启关闭命令：
systemctl status firewalld.service
```
