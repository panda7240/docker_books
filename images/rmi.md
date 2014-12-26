## 删除镜像

查看现有的镜像
```
[root@Mysql dock]# docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
centos              latest              34943839435d        3 weeks ago         224 MB```

#

使用```
docker rmi ```
删除镜像，可以是仓库源或者镜像ID
```
docker rmi centos
docker rmi 34943839435d```

#

如遇无法删除，请删除依赖相关容器
```
docker rm `docker ps -aq````
