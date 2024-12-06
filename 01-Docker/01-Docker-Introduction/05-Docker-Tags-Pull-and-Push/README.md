```
  286  docker images
  287  docker rmi c6e978ccbbb6
  288  docker kill $(docker ps -qa)
  289  docker rm $(docker ps -qa)
  290  docker rmi c6e978ccbbb6
  291  docker images
  292  docker rmi 3b1ebd86c904
  293  docker images
  294  docker push myapache:v1
  295  docker login
  296  docker logout
  297  docker logout -u amitvashist7
  298  docker login -u amitvashist7
  299  docker push myapache:v1
  300  docker tag myapache:v1 amitvashist7/docker-k8s-ey-m-02-dec-2024-myapache:v1
  301  docker images
  302  docker push amitvashist7/docker-k8s-ey-m-02-dec-2024-myapache:v1
  303  docker tag myapache:v2 amitvashist7/docker-k8s-ey-m-02-dec-2024-myapache:v2
  304  docker tag myapache:v3 amitvashist7/docker-k8s-ey-m-02-dec-2024-myapache:v3
  305  docker tag myapache:v4 amitvashist7/docker-k8s-ey-m-02-dec-2024-myapache:v4
  306  docker push amitvashist7/docker-k8s-ey-m-02-dec-2024-myapache:v2
  307  docker push amitvashist7/docker-k8s-ey-m-02-dec-2024-myapache:v3
  308  docker push amitvashist7/docker-k8s-ey-m-02-dec-2024-myapache:v4
  309  docker logout
  310  l
  311  docker rm $(docker ps -qa)
  312  docker images
  313  docker images  -q
  314  docker rmi $(docker images  -q) --force
  315  docker images  -q
  316  docker images
  317  ls
  318  docker run -d amitvashist7/docker-k8s-ey-m-02-dec-2024-myapache:v4
  319  docker ps
  320  docker inspect 7f8a4cf0f558
  321  curl 172.17.0.2
  322  curl 172.17.0.2/info.html
```
