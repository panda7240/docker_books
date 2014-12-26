## 端口映射

Params:

* container (str): The container to look up
* private_port (int): The private port to inspect
* Returns (list of dict): The mapping for the host ports

#

实例

以下两个操作同等效果

```
docker run -d -p 80:80 centos /bin/sleep 30
7174d6347063a83f412fad6124c99cffd25ffe1a0807eb4b7f9cec76ac8cb43b

>>> from docker import Client
>>> c = Client(base_url='tcp://192.168.1.104:2375')
>>> c.port('7174d6347063', 80)
[{'HostIp': '0.0.0.0', 'HostPort': '80'}]```
