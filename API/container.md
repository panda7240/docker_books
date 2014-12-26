## 容器的创建与移除

#### 创建容器

相当与```
docker run```



Params:

* image (str): 要运行的镜像
* command (str or list): 容器运行的命令
* hostname (str): 容器的主机名
* user (str or int): 用户名或UID
* detach (bool): 分离模式：在后台运行的容器，并打印新的容器ID
* stdin_open (bool): 保持标准输入
* tty (bool): 分配一个tty
* mem_limit (float or str): 内存限制 (format: [number][optional unit], where unit = b, k, m, or g)
* ports (list of ints): 端口号列表
* environment (dict or list): A dictionary or a list of strings in the following format ["PASSWORD=xxx"] or {"PASSWORD": "xxx"}.
* dns (list): dns服务器
* volumes (str or list): volumes=['/data']
* volumes_from (str or list): 容器名称或ID的列表，从中获取卷。可选一个字符串用逗号连接容器的id
* network_disabled (bool): 禁止联网
* name (str): 容器名
* entrypoint (str or list): 入口
* cpu_shares (int or float): CPU 权重
* working_dir (str): 工作目录路径
* domainname (str or list): 设置自定义DNS搜索域
* memswap_limit: 内容swap限制



实例
```
>>> from docker import Client
>>> c = Client(base_url='tcp://192.168.1.104:2375')
>>> c.create_container(image='centos',command='echo "examle container"')
{u'Id': u'30b51797743b7b8dd029899bf527797384864fdb3367c18c18748250017f8888',
 u'Warnings': None}```


查看返回结果
```
[root@Mysql ~]# docker ps -a
CONTAINER ID        IMAGE               COMMAND                CREATED             STATUS              PORTS               NAMES
30b51797743b        centos:latest       "echo 'examle contai   27 seconds ago       silly_goldstine  ```

扩展实例

```
c.create_container(image="letong/webserver",stdin_open=True,tty=True,command="/usr/bin/supervisord -c /etc/supervisord.conf",volumes=['/data'],ports=[80,22],name="webserver1")
```

数据绑定实例

```
c.start(container_id, binds={
    '/home/user1/':
        {
            'bind': '/mnt/vol2',
            'ro': False
        },
    '/var/www':
        {
            'bind': '/mnt/vol1',
            'ro': True
        }
})```


#   

#### 移除容器

remove_container

相当于```
docker rm```


Params:

* container (str): 容器ID
* v (bool): 删除与该容器相关联的卷
* link (bool): 删除指定的链接，而不是底层的容器
* force (bool): 强制删除容器

#

实例
```
>>> from docker import Client
>>> c = Client(base_url='tcp://192.168.1.104:2375')
>>> c.remove_container(container='30b5')```

#   
#### 移除镜像



remove_image

相当于```
docker rmi```


Params:

* image (str): 要移除的镜像
* force (bool): 强制移除镜像
* noprune (bool): 不删除未标记的

#

实例

```
>>> from docker import Client
>>> c = Client(base_url='tcp://192.168.1.104:2375')
>>> c.remove_image(image='centos')```
