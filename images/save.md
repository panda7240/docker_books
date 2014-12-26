## 导入和导出

分别用命令```
docker save```
 和 ```
docker load```
 进行导入导出操作，以下为简单的实例。

#

导出镜像
```
docker save -o centos7.tar centos```


#

导入本地镜像
```
sudo docker load --input centos7.tar```
