## 终止与删除容器


使用```docker stop```终止容器

```
[root@Mysql dock]# docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
28c830652ec9        centos:latest       "/bin/bash"         25 minutes ago      Up 2 seconds                            thirsty_albattani   
[root@Mysql dock]# docker stop 28c8
28c8```


使用```docker rm```删除容器
```
[root@Mysql dock]# docker rm 28c8
28c8```

可使用 -f 参数强制删除容器