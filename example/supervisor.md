# Supervisord管理Docker进程

介绍

* 当进程中断或为启用的时候可自动重启


很简单，就直接上Dockefile了
```
# This is a base comment
FROM centos:latest
MAINTAINER letong <a@letong.me>

#yum install Package
RUN yum -y install openssh-server openssh-clients
RUN yum -y install httpd
RUN yum -y install python-setuptools
RUN easy_install supervisor

#set sshd
RUN echo 'root:letong1' | chpasswd

#set supervisor
RUN mkdir -p /var/log/supervisor
ADD supervisord.conf /etc/supervisord.conf

#set port
EXPOSE 22
EXPOSE 80

#set ENV
ENV LANG en_US.UTF-8
ENV LC_ALL en_US.UTF-8

#run supervisor
CMD ["/usr/bin/supervisord -c /etc/supervisord.conf"]```


supervisord的配置
```
[supervisord]
nodaemon=true

[program:sshd]
command=/usr/sbin/sshd -D

[program:httpd]
command=/usr/sbin/httpd -DFOREGROUND```




