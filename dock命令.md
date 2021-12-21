## 基本命令
1. Docker start/stop/restart 命令
  ```
  docker start :启动一个或多个已经被停止的容器

  docker stop :停止一个运行中的容器

  docker restart :重启容器
  ```

2. 删除镜像
```
docker rmi 镜像id
```

3. 删除容器
```
docker rm 容易id
```

4.查看容器和镜像
```
docker ps #查看容器
docker ps -a #已退出的镜像
docker images #查看镜像
```

5. 重启后容器自动重启
```
docker container update --restart=always c3872841c60b
```

6. 创建或修改 /etc/docker/daemon.json 文件，修改为如下形式
```
{
  "registry-mirrors": [
    "https://registry.docker-cn.com",
    "http://hub-mirror.c.163.com",
    "https://docker.mirrors.ustc.edu.cn"
  ]
}
```

```
$ sudo systemctl daemon-reload
$ sudo systemctl restart docker
```

## mysql安装
1. 拉取官方镜像（我们这里选择5.7，如果不写后面的版本号则会自动拉取最新版）
```
docker pull mysql:5.7   # 拉取 mysql 5.7
```
2. 检查是否拉取成功
```
sudo docker images
```
3. 一般来说数据库容器不需要建立目录映射
```
sudo docker run -p 3306:3306 --name mysql -e MYSQL_ROOT_PASSWORD=123456 -d mysql:5.7
```
4. 如果要建立目录映射
```
sudo docker run -p 3306:3306 --name mysql \
-v /usr/local/docker/mysql/conf:/etc/mysql \
-v /usr/local/docker/mysql/logs:/var/log/mysql \
-v /usr/local/docker/mysql/data:/var/lib/mysql \
-e MYSQL_ROOT_PASSWORD=123456 \
-d mysql:5.7
```

5. 检查容器是否正确运行
```
docker container ls
```

## redis 安装
1. 拉取官方镜像
```
docker pull redis
```
2. 运行容器
```
docker run -itd --name redis-test -p 6379:6379 redis
```