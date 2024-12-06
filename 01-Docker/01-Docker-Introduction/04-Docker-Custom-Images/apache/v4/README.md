```
  174  cp -rf v3 v4
  175  ls
  176  cd v4/
  177  ls
  178  vim info.html
  179  ls
  180  vim MyDockerfile
  181  docker build -t myapache:v4 -f MyDockerfile .
  182  vim MyDockerfile
  183  docker build -t myapache:v4 -f MyDockerfile .
  184  docker run -d --name test-apache-5 myapache:v4
  185  docker ps
  186  curl -vv 172.17.0.6:80/info.html

```
