## Dockfile 指令介绍

以下为常用的Dockfile指令，可能不是那么全面。

**FROM**

格式为FROM <image>或```
FROM <image>:<tag>```


第一条指令必须为FROM指令。如果在同一个Dockerfile中创建多个镜像时，可以使用多个FROM指令。

**MAINTAINER**

格式为```
MAINTAINER <name>```
，指定维护者信息。

**RUN**

格式为```
RUN <command>```
或RUN ["executable", "param1", "param2"]。

**CMD**

CMD ["executable","param1","param2"]使用exec执行，一个Dockfile只能有一条CMD，以最后一条为准。

**EXPOSE**

格式为```EXPOSE <port>```，容器暴露的端口号。

**ENV**

格式为```
ENV <key> <value>```
， 指定一个环境变量。

**ADD**

格式为```
ADD <src> <dest>```，src可以是URL或者tar文件。

**COPY**

格式为```
COPY <src> <dest>```，src为本地目录的时候推荐使用 

**VOLUME**

格式为VOLUME ["/data"]，这个就不用过多介绍了。

