#Install K3S via Docker

1. Install
```
curl -s https://raw.githubusercontent.com/rancher/k3d/master/install.sh | bash
* IF NEED TAG
curl -s https://raw.githubusercontent.com/rancher/k3d/master/install.sh | TAG=v1.3.4 bash
```
2. Run
```
k3d create --api-port 6550 --publish 8081:80 --workers 2
export KUBECONFIG="$(k3d get-kubeconfig --name='k3s-default')"
```
3. Demo Nginx
```
kubectl create deployment nginx --image=nginx
kubectl create service clusterip nginx --tcp=80:80

* Run defined yml
kubectl apply -f ./default-nginx.yml

* Test
curl localhost:8081
```

Ref: [rancher/k3d](https://github.com/rancher/k3d)