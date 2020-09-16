### 1. Get started.
Before you start work with Kubernetes you need to install:  
Azure cli - https://docs.microsoft.com/en-us/cli/azure/install-azure-cli  
Kubectl:  
  `az aks install-cli`

### 2. How to login to aks cluster.
  Login to the azure infrastructure:  
  `az login
  az account set --subscription "Microsoft Azure Enterprise MSDN Dev/Test"`  
  Download AKS credentials:  
  `az aks get-credentials --resource-group crgd3 --name crgd3-k8s-01`  
  Check access:  
  `kubectl get nodes`

### 3. How to open the Kubernetes dashboard.
  `az aks browse --resource-group crgd3 --name crgd3-k8s-01`  
  Use kubeconfig authentication to login.  
  By default az aks get-credentials command downloads config to C:\Users\UserName\.kube\config  

### 4. How to get pods and exec to it
  `kubectl get pods`  
  `kubectl exec -it PoD-NaMe -- /bin/bash`  
  
### 5. How copy files from pod
  `kubectl cp default/PoD-NaMe:"FolderBackupInPod" tmp`
------------------------------------------------------------------------------------
$var=Invoke-WebRequest -Method GET -Uri ''
$var.content

$vnetId = az network vnet subnet list --resource-group teamResources-1 --vnet-name vnet --query "[0].id" --output tsv
az aks create --resource-group teamResources-1 --name myAKSClusterTeam2 --network-plugin azure --vnet-subnet-id $vnetId --docker-bridge-address 172.17.0.1/16 --dns-service-op 192.168.0.10 ...

az ad group list --filter "displayname eq 'team2'" -o table
az aks update -g $rg -n $aks -enable-aad --add-admin-group-object-ids GROUPID --aad-tenant-id TENANTID


kubectl get pods -A -o wide
