---
layout: post
title: docker desktop k8s
---

[Docker Desktop for Mac/Windows 开启 Kubernetes](https://github.com/AliyunContainerService/k8s-for-docker-desktop)


# 8001代理
kubectl proxy --address='0.0.0.0' --disable-filter=false --accept-hosts='^localhost$' &

# 服务代理
kubectl port-forward --address='0.0.0.0' service/nginx 80:80 &

TOKEN=$(kubectl -n kube-system describe secret default| awk '$1=="token:"{print $2}')
kubectl config set-credentials kubernetes-dashboard --token="${TOKEN}"
echo $TOKEN

get deployments  
get pods  
get services  
kubectl describe deployment nginx-deployment  
kubectl describe service nginx  
kubectl delete ...  
