level3

```
# 创建我们的docker-compose文件
mkdir /docker-compose/yml01
# 编写我们的yaml文件
```

![](C:\Users\86138\Pictures\data\level3.0.png)

```
# 使用docker-compose编排我们刚刚写好的yml文件
docker-compose up -d
# 查看我们运行的容器
docker-compose ps
# 进入我们的容器，看看是否已经安装了ping命令
docker exec -it test1 bash
cd data
cat a.txt
```

![](C:\Users\86138\Pictures\data\level3.1.png)

```
# 我们停止我们的容器再去本地看看我们的数据
docker-compose stop
cd /container_data/data2
cat a.txt
```

![](C:\Users\86138\Pictures\data\level3.2.png)

![](C:\Users\86138\Pictures\data\level3.3.png)

```
# 上传镜像到仓库
docker commit test1 level3_test1:v1.0.0
docker commit test2 level3_test2:v1.0.0
docker tag level3_test1:v1.0.0 kinsomnia/level3_test1
docker tag level3_test2:v1.0.0 kinsomnia/level3_test2
# 提前登录
docker push kinsomnia/level3_test1
docker push kinsomnia/level3_test2
```

![](C:\Users\86138\Pictures\data\level3.4.png)