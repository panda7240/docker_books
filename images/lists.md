## 查看镜像

显示本地已有的镜像
```
[root@Mysql ~]# docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
centos              latest              34943839435d        3 weeks ago         224 MB
```

参数注释
* REPOSITOR：仓库来源
* TAG：镜像标
* IMAGE ID：镜像ID，具有唯一性
* CREATED：镜像创建的时间
* VIRTUAL SIZE：镜像大小

有时会出现相同ID的不同TAG，不用担心那是同一镜像。