## 获取镜像

相当于```
docker pull```


Params:

* repository (str): 仓库
* tag (str): tag
* stream (bool): Stream the output as a generator
* insecure_registry (bool): Use an insecure registry


```
>>> from docker import Client
>>> c = Client(base_url='tcp://192.168.1.104:2375')
>>> c.pull(repository='centos',tag='centos6')```
