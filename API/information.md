## 详细信息查询

查看系统信息

```
>>> from docker import Client
>>> c = Client(base_url='tcp://192.168.1.104:2375')
>>> c.info()
{u'Containers': 1,
 u'Debug': 0,
 u'Driver': u'devicemapper',
 u'DriverStatus': [[u'Pool Name', u'docker-253:1-8812760-pool'],
  [u'Pool Blocksize', u'65.54 kB'],
  [u'Data file', u'/var/lib/docker/devicemapper/devicemapper/data'],
  [u'Metadata file', u'/var/lib/docker/devicemapper/devicemapper/metadata'],
  [u'Data Space Used', u'1.209 GB'],
  [u'Data Space Total', u'107.4 GB'],
  ......```

查看镜像底层信息

```
>>> from docker import Client
>>> c = Client(base_url='tcp://192.168.1.104:2375')
>>> c.inspect_image(image_id='2a32')
{u'Architecture': u'amd64',
 u'Author': u'',
 u'Comment': u'Imported from -',
 u'Config': None,
 u'Container': u'',
 u'ContainerConfig': {u'AttachStderr': False,
  u'AttachStdin': False,
  u'AttachStdout': False,
  u'Cmd': None,
  u'CpuShares': 0,
  u'Cpuset': u'',
  ......```

查看容器底层信息

```
c.inspect_container(container='38aa')```

