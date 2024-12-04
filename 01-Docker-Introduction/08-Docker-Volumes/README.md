## Docker Volumes 

```
  455  docker volume ls
  456  docker volume create myvol1
  457  docker volume ls
  458  docker volume inspect myvol1
  459  ls -ltr /var/lib/docker/volumes/myvol1/
  460  ls -ltr /var/lib/docker/volumes/myvol1/_data/
  461  docker images
  462  docker run -it --name stg-1 -v myvol1:/myapp ubuntu
  463  ls
  464  docker ps
  465  docker kill $(docker ps -q)
  466  docker rm $(docker ps -aq)
  467  docker ps -a
  468  docker volume ls
  469  ls -ltr /var/lib/docker/volumes/myvol1/_data/
  470  cat  /var/lib/docker/volumes/myvol1/_data/info
  471  hostname >> /var/lib/docker/volumes/myvol1/_data/info
  472  pwd >> /var/lib/docker/volumes/myvol1/_data/info
  473  cat  /var/lib/docker/volumes/myvol1/_data/info
  474  docker run -it --name stg-2 -v myvol1:/myapp2 ubuntu
  475  docker run -it --name stg-3 -v myvol1:/myapp2 ubuntu
  476  docker ps
  477  docker run -it --name stg-4 -v myvol1:/myapp2:ro ubuntu
  478  ls
  479  docker volume ls
  480  docker run -it --name stg-5 -v myvol1 ubuntu
  481  docker ps
  482  docker inspect stg-5
  483  docker volume ls
  484  cat  /var/lib/docker/volumes/0424e2fed09d8e520f00cbeeecabe37778d0d8fd45a6170593440b45128908aa/_data/hello.txt
  485  ls
  486  docker ps
  487  docker volume ls
  488  pwd
  489  docker run -it --name stg-6 -v /root/docker-k8s-EY-M-02-Dec-2024:myvol3 ubuntu
  490  docker run -it --name stg-7 -v /root/docker-k8s-EY-M-02-Dec-2024:/myvol3 ubuntu
  491  ls
  492  docker run -it --name stg-8 -v /root/docker-k8s-EY-M-02-Dec-2024:/myvol3:ro ubuntu
```


## Clean Up 
```
  500  docker kill $(docker ps -q)
  501  docker rm $(docker ps -q)
  502  docker rm $(docker ps -qa)
  503  docker volume ls
  504  docker volume ls -q
  505  docker volume rm $(docker volume ls -q)
  506  docker volume ls

```
