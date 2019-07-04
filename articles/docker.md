### docker使用以及常用命令整理

#### 安装
  在官网下载 dmg文件直接安装即可
  
  1. 查看docker 信息,列出容器数量，镜像数量，运行情况等信息
  ```
      docker info
  ```
  2. 
  ```
      docker --version
  ```
  
#### 镜像
（tip 镜像和容器的区别：镜像是容器的基础，一个容器相当于一个Linux的系统环境）
1. 获取镜像 docker pull 镜像名字:版本号

```
docker pull ubuntu:12.04 // 获取
docker pull kylinchang/demo:tagname //(从registry.hub.docker.com 获取)
```

2. 列出镜像 docker images

3. 利用镜像启动容器 docker run ,会进入一个与容器交互的终端

```
docker run -t -i ouruser/sinatra:v2 /bin/bash
```

-t:在新容器内指定一个伪终端或终端

-i:允许你对容器内的标准输入 (STDIN) 进行交互

4. 修改已有镜像 docker commit,

```
docker commit -m "Added json gem" -a "Docker Newbee" 0b2616b0e5a8 ouruser/sinatra:v2

```
在上一步的基础上 在终端中操作，然后用docker commit 提交。 
-m 修改的信息
-a 作者
0b2616b0e5a8 容器ID
ouruser/sinatra:v2 镜像名字 & 标签

5. 发布修改镜像

```
docker push ouruser/sinatra:v2
```

#### 容器

1. 启动容器 docker run 

```
docker run -t -i  ubuntu:12.04 /etc/bash
```
可附带的命令
-t 选项让Docker分配一个伪终端（pseudo-tty）并绑定到容器的标准输入上，
-i 则让容器的标准输入保持打开
-d 参数时，容器启动后会进入后台。

2. 启动容器 docker start containerName

```
docker start ubutu
```
ubutu 是容器的名字

3. 容器进程信息 docker ps  如果需要查看全部加 -a

4. 终止容器 docker stop containerName

5. 重新启动容器 docker restart containerName

6. 进入容器 docker attach containerName

7. 删除容器 docker rm containerName  如果要删除运行中的容器 加-f

#### 数据卷

1. 挂在数据卷
```
docker run -d -P --name web -v /src/webapp:/opt/webapp training/webapp
```
-P 端口映射
--name 指定容器名字
-v /src/webapp:/opt/webapp 指定数据卷映射 /src/webapp为主机目录  /opt/webapp为容器目录

