# azure-kubernetes-service-networking

az aks get-credentials --resource-group "AKS-Cloud" --name ExistingNetwork
kubectl config use-context 'CSCluster'


kubectl get pods -o wide
kubectl get service --watch
kubectl get service hello-world-loadbalancer



$NODE=$(kubectl get nodes -o jsonpath='{ .items[0].metadata.name }')
kubectl debug node/$NODE -it --image=ubuntu
#kubectl debug node/$NODENAME -it --image=mcr.microsoft.com/aks/fundamental/base-ubuntu:v0.0.11
apt-get update && apt-get install curl -y


kubectl create deployment hello-world-clusterip `
    --image=gcr.io/google-samples/hello-app:1.0

kubectl describe service hello-world-clusterip

kubectl delete deployments hello-world-clusterip
kubectl delete service hello-world-clusterip

