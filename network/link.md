## 容器互联


运行一个名web的容器，与名为db的容器互联。link格式为 name:alias

```
docker run -d -P --name web --link db:db  webserver /bin/bash```
