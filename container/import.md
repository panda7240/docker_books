## 导入和导出

使用```
docker export```
 导出
 
```
[root@Mysql dock]# docker ps -a
CONTAINER ID        IMAGE               COMMAND                CREATED             STATUS                         PORTS               NAMES
52a3ed388019        centos:latest       "/bin/echo hhaha"      3 minutes ago       Exited (0) 3 minutes ago                           mad_nobel 
[root@Mysql dock]# docker export 52a3 > centos7.tar
[root@Mysql dock]# ll centos7.tar 
-rw-r--r--. 1 root root 232501760 12月 25 13:59 centos7.tar```


使用```
docker import```
 导入
```
[root@Mysql dock]# docker import
Usage: docker import URL|- [REPOSITORY[:TAG]]

[root@Mysql dock]# cat centos7.tar | docker import - letong/centos:v1
2a32c43f599401817a5fb7b82b0a18d9898a1d3145f541b0bea65cf40611c121
[root@Mysql dock]# docker images
REPOSITORY          TAG                 IMAGE ID            CREATED              VIRTUAL SIZE
letong/centos       v1                  2a32c43f5994        About a minute ago   224 MB
```

