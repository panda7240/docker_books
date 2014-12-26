## 简单示例

以下是一段简单的sshd的示例，EXPOSE暴露的端口仅供互联系统使用。
```
# This is a base comment
FROM centos:latest
MAINTAINER letong <a@letong.me>

#yum install Package
RUN yum -y install openssh-server openssh-clients

#set sshd
RUN echo 'root:letong1' | chpasswd

#set port
EXPOSE 22

#set ENV
ENV LANG en_US.UTF-8
ENV LC_ALL en_US.UTF-8

#run sshd
CMD ["/usr/sbin/sshd -D"]
```

