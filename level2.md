level1

```
mkdir dockerfiles # 创建文件夹
cd dockerfiles
cat yuyulin.txt > index.html
vim dockerfile # 编写dockerfile文件
```

![](https://github.com/Kinsomnia/data_picture/blob/main/level2.2.png)

```
docker build -t mynginx:v1 .
docker run -d --name mynginx -p 8080:80 mynginx:v1
curl localhost:8080
```

![](https://github.com/Kinsomnia/data_picture/blob/main/level2.1.png)

```
docker tag myngix:v1 kinsomnia/mynginx   # 重命名一下我们刚才镜像
docker push kinsomnia/mynginx  # 上传到dockerhub
```

![](https://github.com/Kinsomnia/data_picture/blob/main/level2.3.png)

![](https://github.com/Kinsomnia/data_picture/blob/main/level2.5.png)

```
docker pull kinsomnia/mynginx 
docker run -d --name mynginx -p 8080:80 kinsomnia/mynginx  # 把我们上传的镜像拉下来再跑一次
```

![](https://github.com/Kinsomnia/data_picture/blob/main/level2.4.png)
