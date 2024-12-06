```
  551  docker-compose up -d
  552  docker-compose ps
```

```
root@ubuntugui:~/docker-k8s-EY-M-02-Dec-2024/02-Docker-Compose/05-WebApp-with-Network-and-Volume# docker-compose ps
NAME                                         COMMAND                  SERVICE             STATUS              PORTS
05-webapp-with-network-and-volume-db-1       "/docker-entrypoint.…"   db                  running             0.0.0.0:3306->80/tcp, :::3306->80/tcp
05-webapp-with-network-and-volume-middle-1   "/usr/sbin/apache2ct…"   middle              running             0.0.0.0:9000->80/tcp, :::9000->80/tcp
05-webapp-with-network-and-volume-proxy-1    "/docker-entrypoint.…"   proxy               running             0.0.0.0:8099->80/tcp, :::8099->80/tcp
root@ubuntugui:~/docker-k8s-EY-M-02-Dec-2024/02-Docker-Compose/05-WebApp-with-Network-and-Volume#
```
```
root@ubuntugui:~/docker-k8s-EY-M-02-Dec-2024/02-Docker-Compose/05-WebApp-with-Network-and-Volume# ls
README.md  docker-compose.yaml
```
```
root@ubuntugui:~/docker-k8s-EY-M-02-Dec-2024/02-Docker-Compose/05-WebApp-with-Network-and-Volume# docker volume ls
DRIVER    VOLUME NAME
local     05-webapp-with-network-and-volume_mydb-app-vol1
local     05-webapp-with-network-and-volume_mymiddle-app-vol1
local     05-webapp-with-network-and-volume_myproxy-app-vol1
local     05-webapp-with-network-and-volume_myproxy-app-vol2
```
```
root@ubuntugui:~/docker-k8s-EY-M-02-Dec-2024/02-Docker-Compose/05-WebApp-with-Network-and-Volume# docker network ls
NETWORK ID     NAME                                             DRIVER    SCOPE
b6c558e38f4f   02-nginx-deployment_default                      bridge    local
7ae2518fd265   03-myapp-deployment_default                      bridge    local
eed11258594e   04-build_default                                 bridge    local
3adfef96307d   05-webapp-with-network-and-volume_mynet          bridge    local
1b5548ca4739   05-webapp-with-network-and-volume_mysecure-net   bridge    local
d1966e676928   bridge                                           bridge    local
c308ea90e6af   host                                             host      local
5171cc5c52ee   mybr0                                            bridge    local
33774f98eeec   none                                             null      local
root@ubuntugui:~/docker-k8s-EY-M-02-Dec-2024/02-Docker-Compose/05-WebApp-with-Network-and-Volume#

```
