```
# 拉取镜像并运行
docker run -d --name mynginx -p 8000:80 nginx
# 如果容器名被占用可以用如下命令删除容器名
docker container rm name
```

![text1](C:\Users\86138\Pictures\Screenshots\屏幕截图_20221128_161707.png)

```
# 访问
curl localhost:8000
# 进入容器
docker exec -it mynginx bash
# 修改访问页面
echo "xxxx" > /usr/share/nginx/html/index.html
exit
# 再次访问既可以看到被修改的内容
curl localhost:8000
```

![](C:\Users\86138\Pictures\Screenshots\屏幕截图_20221128_161735.png)

```
# 把容器重新打成新的镜像
docker commit mynginx mynginx:v1.0.0
# 查看我们的新镜像
docker images
```

![](C:\Users\86138\Pictures\Screenshots\屏幕截图_20221128_161922.png)

```
# 重跑我们刚才的镜像
docker run -d --name mynginx1 -p 8080:80 mynginx:v1.0.0
# 访问(8000,8080都是被修改后的)
curl localhost:8080
curl localhost:8000
```

![](C:\Users\86138\Pictures\Screenshots\屏幕截图_20221128_162223.png)
