## 容器数据卷管理

使用-v参数将本地目录挂载到容器中
```
docker run -d -P --name web -v /src/webapp:/opt/webapp training/webapp python app.py```




如果你想让该容器对数据拥有只读权
```
docker run -d -P --name web -v /src/webapp:/opt/webapp:ro training/webapp python app.py```

#

创建一个挂在数据卷的容器
如果你想要容器之间数据共享，或者从非持久化容器中使用一些持久化数据，最好创建一个名为数据卷的容器，然后用它挂载数据。

让我们创建一个数据共享命名的容器。

```
docker run -d -v /dbdata --name dbdata training/postgres```

你可以使用--volumes-from标识来再另外一个容器挂载/dbdata卷。

```
docker run -d --volumes-from dbdata --name db1 training/postgres
docker run -d --volumes-from dbdata --name db2 training/postgres```

您也可以使用多个--volumes-from参数来将多个数据卷桥接到多个容器中。


也可以重复挂载
```
docker run -d --name db3 --volumes-from db1 training/postgres```

当你删除挂载卷的dbdata容器，包括初始化数据化容器，或者随后的db1容器和db2容器，该卷将不会被删除直到没有容器使用该卷。这允许你升级，或者把有效的数据卷在容器之间迁移。

#

备份数据卷

```
docker run --volumes-from dbdata -v /backup ubuntu tar cvf /backup/backup.tar /dbdata```


恢复数据卷，先运行一个容器，再新的容器的卷标中解压备份文件

```
docker run -v /dbdata --name dbdata2 ubuntu /bin/bash
docker run --volumes-from dbdata2 -v /backup busybox tar xvf /backup/backup.tar ```


