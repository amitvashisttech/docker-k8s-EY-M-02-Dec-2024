## Container CLI Introduction
```
  622  docker version
  623  systemctl status docker
  624  docker images
  625  docker run hello-world
  626  docker container ls
  627  docker container ls -a
  628  docker run --name test-av-1 hello-world
  629  docker container ls
  630  docker container ls -a
  631  docker run --name test-av-1 hello-world
  632  docker run --name test-av-2 hello-world
  633  docker run -d  --name test-av-3 hello-world
  634  docker container ls -a
  635  docker run -it --name test-ubuntu-1 ubuntu bash
  636  cat /etc/os-release
  637  docker run -it --name test-ubuntu-1 ubuntu bash
  638  docker run -it --name test-ubuntu-2 ubuntu:18.04 bash
  639  docker run -it --name test-ubuntu-3 ubuntu:18.04 bash
  640  docker ps
  641  docker ps -a
  642  docker start test-ubuntu-1
  643  docker ps -a
  644  docker attach 6d65981b8444
       docker logs -f <container-id / name >
       docker exec -it <container-id / name > ps -ef 

```

## Format Commands

```
   45  docker inspect $(docker ps -l) 
   46  docker ps -l
   47  docker ps -l -q 
   48  docker inspect $(docker ps -lq) 
   49  docker ps 
   50  docker ps -q
   51  docker inspect $(docker ps -q)
   52  docker inspect $(docker ps -q) | wc -l 
   53  docker ps 
   54  docker run -itd ubuntu top 
   55  docker ps 
   56  docker inspect --format '{{.Name}} {{.State.Running}} {{.NetworkSettings.IPAddress}}' $(docker ps -q)
   57  docker inspect --format '{{.Name}} - {{.State.Running}} - {{.NetworkSettings.IPAddress}}' $(docker ps -q)
   58  docker inspect --format '{{.Name}} - {{.State.Running}} - {{.NetworkSettings.IPAddress}}' $(docker ps -qa)

```


## Clean UP 
```
  57  docker ps
   58  docker stop test-ubuntu-5
   59  docker ps
   60  docker kill test-ubuntu-4
   61  docker ps
   62* docker
   63  docker start test-ubuntu-5
   64  docker ps
   65  docker start test-ubuntu-4
   66  docker ps
   67  docker kill test-ubuntu-4
   68  docker kill test-ubuntu-5
   69  docker ps -a
   70  docker rm test-ubuntu-5
   71  docker ps -a
   72  docker ps -aq
   73  docker rm $(docker ps -aq )
   74  docker ps -a
   75  docker images
   76  docker rmi fec8bfd95b54
   77  docker rmi fec8bfd95b54 --force
   78  docker images
   79  docker images -q
   80  docker rmi $(docker images -q) --force
   81  docker images
   82  docker ps -a
```
