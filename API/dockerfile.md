## 使用Dockerfile

**build格式**

build(self, path=None, tag=None, quiet=False, fileobj=None, nocache=False, rm=False, stream=False, timeout=None, custom_context=False, encoding=None)


Params:

* path (str): Path to the directory containing the Dockerfile
* tag (str): A tag to add to the final image
* quiet (bool): Whether to return the status
* fileobj: A file object to use as the Dockerfile. (Or a file-like object)
* nocache (bool): Don't use the cache when set to True
* rm (bool): Remove intermediate containers
* stream (bool): Return a blocking generator you can iterate over to retrieve build output as it happens
* timeout (int): HTTP timeout
* custom_context (bool): Optional if using fileobj
* encoding (str): The encoding for a stream. Set to gzip for compressing

实例

```
>>> from io import BytesIO
>>> from docker import Client
>>> dockerfile = '''
... # Shared Volume
... FROM centos:latest
... MAINTAINER letong <a@letong.me>
... VOLUME /data
... CMD ["/bin/sh"]
... '''
>>> f = BytesIO(dockerfile.encode('utf-8'))
>>> c = Client(base_url='tcp://127.0.0.1:2375')
>>> c.built(path=/dockerfile, tag='letong/webserver')```

