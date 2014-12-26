## docker-py 文档

简易安装
```
pip install docker-py```

完整的文档在 /docs/ 目录

GitHub项目链接：

https://github.com/docker/docker-py

启动远程socket

**Centos**

OPTIONS=--selinux-enabled -H fd:// -H tcp://0.0.0.0:2375

**Ubuntu**

DOCKER_OPTS="-H tcp://0.0.0.0:2375 -H unix:///var/run/docker.sock"


#

example

```
In [1]: from docker import Client
In [2]: c = Client(base_url='tcp://192.168.1.104:2375')
In [3]: c.info()
Out[3]: 
{u'Containers': 6,
 u'Debug': 0,
 u'Driver': u'devicemapper',
 u'DriverStatus': [[u'Pool Name', u'docker-253:1-8812760-pool'],
  [u'Pool Blocksize', u'65.54 kB'],
  [u'Data file', u'/var/lib/docker/devicemapper/devicemapper/data'],
  [u'Metadata file', u'/var/lib/docker/devicemapper/devicemapper/metadata'],
  [u'Data Space Used', u'1.219 GB'],
  [u'Data Space Total', u'107.4 GB'],
  [u'Metadata Space Used', u'2.175 MB'],
  [u'Metadata Space Total', u'2.147 GB'],
  [u'Library Version', u'1.02.84-RHEL7 (2014-03-26)']],
 u'ExecutionDriver': u'native-0.2',
 u'IPv4Forwarding': 1,
 u'Images': 18,
 u'IndexServerAddress': u'https://index.docker.io/v1/',
 u'InitPath': u'/usr/libexec/docker/dockerinit',
 u'InitSha1': u'c906504aa058139c1d0569ecd0aa5f462a73440f',
 u'KernelVersion': u'3.10.0-123.el7.x86_64',
 u'MemoryLimit': 1,
 u'NEventsListener': 0,
 u'NFd': 12,
 u'NGoroutines': 12,
 u'OperatingSystem': u'CentOS Linux 7 (Core)',
 u'SwapLimit': 1}```
