## 查看镜像

相当于```
docker images```

Params:

* name (str): 匹配name
* quiet (bool): 只显示ID，返回列表
* all (bool): 显示所有镜像
* viz: Depreciated

#

实例

```
>>> from docker import Client
>>> c = Client(base_url='tcp://192.168.1.104:2375')
>>> c.images(name='centos')
[{u'Created': 1417557342,
  u'Id': u'34943839435dfb2ee646b692eebb06af13823a680ace00c0adc232c437c4f90c',
  u'ParentId': u'5b12ef8fd57065237a6833039acc0e7f68e363c15d8abb5cacce7143a1f7de8a',
  u'RepoTags': [u'centos:latest'],
  u'Size': 224015991,
  u'VirtualSize': 224015991}]
```
