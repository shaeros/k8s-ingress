### k8s-ingress

k8s ingress 搭建

创建backend时需要去国外网站拉镜像，防火墙原因，做如下处理：

1、docker pull mirrorgooglecontainers/defaultbackend-amd64:1.5

2、docker tag mirrorgooglecontainers/defaultbackend-amd64:1.5 k8s.gcr.io/defaultbackend-amd64:1.5
