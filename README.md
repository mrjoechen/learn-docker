# learn-docker

### docker


##### 查看镜像列表


```
  docker images
```

###### 以镜像启动容器


```
  docker run
  
  example: docker run -d -u root -p 80:8080 jenkins
  
  -d 以守护线程方式(后台)运行。不加该参数，关掉命令行，docker的jenkins就随之停止了。

  -u jenkins的Linux启动用户名

  -p  端口映射 docker命令所有映射，都是真系统的在前，docker下的在后 例如 -p 80:8080  就是把docker下的8080端口映射到真正系统上的80端口对外访问
```

###### 查看正在运行容器


```
  docker ps
```
###### 进入正在运行容器


```
  docker exec -it 64e3220bc736 /bin/bash
  
    -t让Docker分配一个伪终端并绑定在容器的标准输入上，-i让容器的标准输入保持打开。
  或
  docker exec -it 64e3220bc736 /bin/sh
```
<img src="https://github.com/mrjoechen/learn-docker/blob/master/images/1562312427827.jpg"/>

###### docker 删除镜像
```
  docker rmi [options "o">] <image>  "o">[image...]
  docker rmi nginx:latest postgres:latest python:latest
  
  从本地移除一个或多个指定的镜像。

-f 强行移除该镜像，即使其正被使用；
```


###### docker 删除容器
```
  docker rm [options "o">] <container>  "o">[container...]
  docker rm nginx-01 nginx-02 db-01 db-02
  sudo docker rm -l /webapp/redis
  -f 强行移除该容器，即使其正在运行；
  -l 移除容器间的网络连接，而非容器本身；
  -v 移除与容器关联的空间。
 ```
