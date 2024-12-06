```
543  cd 02-Docker-Compose/
  544  ls
  545  mkdir 02-Nginx-Deployment
  546  ls
  547  cd 02-Nginx-Deployment/
  548  ls
  549  vim docker-compose.yaml
  550  ls
  551  docker-compose up -d
  552  docker-compose ps
  553  curl localhost:8097
  554  docker-compose ps
  555  docker-compose stop
  556  docker-compose rm
```

```
root@ubuntugui:~/docker-k8s-EY-M-02-Dec-2024/02-Docker-Compose/03-MyApp-Deployment# docker-compose up -d
[+] Running 4/4
 ⠿ Network 03-myapp-deployment_default     Created                                                                                                               0.1s
 ⠿ Container 03-myapp-deployment-db-1      Started                                                                                                               1.1s
 ⠿ Container 03-myapp-deployment-proxy-1   Started                                                                                                               1.1s
 ⠿ Container 03-myapp-deployment-middle-1  Started                                                                                                               1.0s
```

```
root@ubuntugui:~/docker-k8s-EY-M-02-Dec-2024/02-Docker-Compose/03-MyApp-Deployment# docker-compose ps
NAME                           COMMAND                  SERVICE             STATUS              PORTS
03-myapp-deployment-db-1       "/docker-entrypoint.…"   db                  running             0.0.0.0:3306->80/tcp, :::3306->80/tcp
03-myapp-deployment-middle-1   "/usr/sbin/apache2ct…"   middle              running             0.0.0.0:9000->80/tcp, :::9000->80/tcp
03-myapp-deployment-proxy-1    "/docker-entrypoint.…"   proxy               running             0.0.0.0:8099->80/tcp, :::8099->80/tcp
root@ubuntugui:~/docker-k8s-EY-M-02-Dec-2024/02-Docker-Compose/03-MyApp-Deployment# docker-compose kill 03-myapp-deployment-middle-1
```
no such service: 03-myapp-deployment-middle-1
```
root@ubuntugui:~/docker-k8s-EY-M-02-Dec-2024/02-Docker-Compose/03-MyApp-Deployment# docker-compose kill middle
[+] Running 1/1
 ⠿ Container 03-myapp-deployment-middle-1  Killed                                                                                                                0.7s
```
```
root@ubuntugui:~/docker-k8s-EY-M-02-Dec-2024/02-Docker-Compose/03-MyApp-Deployment# docker-compose ps
NAME                           COMMAND                  SERVICE             STATUS              PORTS
03-myapp-deployment-db-1       "/docker-entrypoint.…"   db                  running             0.0.0.0:3306->80/tcp, :::3306->80/tcp
03-myapp-deployment-middle-1   "/usr/sbin/apache2ct…"   middle              exited (137)
03-myapp-deployment-proxy-1    "/docker-entrypoint.…"   proxy               running             0.0.0.0:8099->80/tcp, :::8099->80/tcp
```
```
root@ubuntugui:~/docker-k8s-EY-M-02-Dec-2024/02-Docker-Compose/03-MyApp-Deployment# docker-compose start middle
[+] Running 1/1
 ⠿ Container 03-myapp-deployment-middle-1  Started                                                                                                               0.3s
```
```
root@ubuntugui:~/docker-k8s-EY-M-02-Dec-2024/02-Docker-Compose/03-MyApp-Deployment# docker-compose ps
NAME                           COMMAND                  SERVICE             STATUS              PORTS
03-myapp-deployment-db-1       "/docker-entrypoint.…"   db                  running             0.0.0.0:3306->80/tcp, :::3306->80/tcp
03-myapp-deployment-middle-1   "/usr/sbin/apache2ct…"   middle              running             0.0.0.0:9000->80/tcp, :::9000->80/tcp
03-myapp-deployment-proxy-1    "/docker-entrypoint.…"   proxy               running             0.0.0.0:8099->80/tcp, :::8099->80/tcp
root@ubuntugui:~/docker-k8s-EY-M-02-Dec-2024/02-Docker-Compose/03-MyApp-Deployment#

```
