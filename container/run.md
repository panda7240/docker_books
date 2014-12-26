## 运行容器

使用```
docker run```
 运行容器

```
[root@Mysql dock]# docker run -ti centos /bin/bash
[root@28c830652ec9 /]# ```

后台启动容器，echo命令一瞬间就结束了，只能使用ps -a查看停止的容器
```
[root@Mysql dock]# docker run -d centos /bin/echo "hhaha"
52a3ed388019ff6a2094d1c5c8e2ae08a51a3308ffcfa3ac5b5661836ee9e627
```



使用```
docker start```
启动已经停止的容器
```
[root@Mysql dock]# docker start 28c8
28c8
[root@Mysql dock]# docker ps
```
以上使用的是容器的ID号，可简写

