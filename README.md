# Login to Azure / set subscription
$Subscription = "AzIntConsumption"
Connect-AzAccount -Subscription $subscription

# Disconnect-AzAccount


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

openssl req -x509 -nodes -days 365 -newkey rsa:2048 `
    -keyout tls.key -out tls.crt -subj "/C=US/ST=ILLINOIS/L=CHICAGO/O=IT/OU=IT/CN=tls.example.com"
kubectl create secret tls tls-secret --key tls.key --cert tls.crt
kubectl delete secret tls-secret



az vm update --resource-group fileservers --name FileSrvE2 --set osProfile.windowsConfiguration.enableAutomaticUpdates=true osProfile.windowsConfiguration.patchSettings.patchMode=AutomaticByPlatform
az vm update --resource-group fileservers --name FileSrv2E2 --set osProfile.windowsConfiguration.enableAutomaticUpdates=true osProfile.windowsConfiguration.patchSettings.patchMode=AutomaticByPlatform