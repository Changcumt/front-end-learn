## 配置Linux服务器

服务器版本 centos 6.1
47.102.114.231  kylin / P52nRc7J8n1HNgUk

#### 查看系统版本信息
```bash
// 查看系统信息
$ uname -a

// 系统版本信息
$ head -n 1 /etc/issue

//or
$ lsb_release -a
```

#### 关闭apache

centos 一般情况下会开启apache，为了使用nginx，需要把apache停掉

```bash
// 关闭apache
sudo service httpd stop

// 查看httpd 是否开机启动
chkconfig --list

// 如果设置了开机启动 需要关闭

chkconfig httpd off

```

#### 安装nginx

```bash
// 安装 nginx依赖以及nginx
$   yum install gcc-c++
$   yum install pcre pcre-devel
$   yum install zlib zlib-devel
$   yum install openssl openssl-devel
$   yum install nginx

// 设置开机启动（版本不一样 可能命令也不一样）
systemctl enable nginx.service 
// or
chkconfig nginx on

// nginx相关服务
service nginx start
service nginx restart
service nginx stop
```

#### 安装node

```bash
// 下载包
wget https://npm.taobao.org/mirrors/node/v10.16.2/node-v10.16.2-linux-x64.tar.xz
// 解压
tar -xvf node-v10.16.2-linux-x64.tar.xz 
// 重命名 
mv node-v10.16.2-linux-x64 nodejs
//软连接
sudo ln -s /home/kylin/tools/nodejs/bin/node /usr/local/bin/
sudo ln -s /home/kylin/tools/nodejs/bin/npm /usr/local/bin/
```

#### 安装mongodb
```bash
yum install -y mongodb-server mongodb
// 启动命令  
service mongod start
// restart命令  
service mongod restart
// stop命令  
service mongodb stop

// 配置文件  /etc/mongod.conf

// 进入mongodb 环境
mongo

```


#### 安装redis 
[参考](https://www.cnblogs.com/rslai/p/8249812.html)
```
yum install epel-release
yum install redis

# 启动redis
service redis start
# 停止redis
service redis stop
# 查看redis运行状态
service redis status


# 进入本机redis
redis-cli
# 列出所有key
keys *
```
