## 获取镜像

通过pull获取镜像
```
docker pull centos```

默认为官方源，速度较慢，可以使用国内源
```
docker pull dl.dockerpool.com:5000/centos
docker pull docker.cn/docker/centos```


或者修改配置文件

ubuntu中的配置文件：/etc/default/docker

Centos中的配置文件：/etc/sysconfig/docker

#   
以下为Ubuntu中的配置文件示例 
```
DOCKER_OPTS="--dns 8.8.8.8 --dns 8.8.4.4 --insecure-registry dl.dockerpool.com:5000```
