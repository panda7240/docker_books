## 端口映射

将宿主机的2222端口映射到容器的22端口，并启动sshd服务。
```
docker run -d -p 127.0.0.1:2222:22 webserver /usr/sbin/sshd -D```



