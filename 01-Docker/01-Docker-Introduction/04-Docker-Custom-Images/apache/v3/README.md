```
   91  cd 04-Docker-Custom-Images/
   92  ls
   93  docker images
   94  docker run -it ubuntu:noble
   95  ls
   96  mkdir apache/v1 -p
   97  ls
   98  cd apache/v1/
   99  ls
  100  vim Dockerfile
  101  ls
  102  docker build -t myapache:v1 .
  103  docker --debug
  104  docker images
  105  docker run -d --name test-apache-1 myapache:v1
  106  docker ps
  107  docker inspect test-apache-1
  108  curl 172.17.0.2
```
