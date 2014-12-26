## 启动与终止

#### 启动容器

Params:

* container (str): 启动的容器
* binds: 数据挂载绑定
* port_bindings (dict): 端口绑定
* lxc_conf (dict): LXC配置
* publish_all_ports (bool): 发布所有端口的主机
* links (dict or list of tuples): See note above
* privileged (bool): 给扩展权限到这个容器
* dns (list): 设置自定义DNS服务器
* dns_search (list): DNS搜索域
* volumes_from (str or list): 容器名称或ID的列表，从中获取卷。可选一个字符串用逗号连接容器的id
* network_mode (str): One of ['bridge', None, 'container:<name|id>',
'host']
* restart_policy (dict): See note above. "Name" param must be one of ['on-failure', 'always']

#

实例

```
>>> from docker import Client
>>> c = Client(base_url='tcp://192.168.1.104:2375')
>>> container = cli.create_container(image='busybox:latest', command='/bin/sleep 30')
>>> c.start(container=container.get('Id'))```



#   
#### 停止容器


Params:

* container (str): 要移除的容器
* timeout (int): 超时时间，否则强制停止


#

实例
```
>>> from docker import Client
>>> c = Client(base_url='tcp://192.168.1.104:2375')
>>> c.stop(container='8290')```


