
# k8s ingress 搭建

### 创建namespace
kubectl create -f namespace.yaml

### 创建role
kubectl create -f rabc.yaml

### 创建configmap
kubectl create -f configmap.yaml

### 创建ingress服务
kubectl create -f with-rabc.yaml

### 创建backend
kubectl create -f backend.yaml

创建backend时需要去国外网站拉镜像，防火墙原因，做如下处理：

1、docker pull mirrorgooglecontainers/defaultbackend-amd64:1.5

2、docker tag mirrorgooglecontainers/defaultbackend-amd64:1.5 k8s.gcr.io/defaultbackend-amd64:1.5

### 部署一个ingress-controller的service nodePort
如果需要集群外部访问，就需要部署一个NodePort的service 用来提供外部访问
kubectl create -f service-nodeport.yaml

### 创建访问应用的ingress
kubectl create -f deplpy-demo.yaml ingress-hello.yaml ingress-myapp.yaml ingress-track.yaml
