# 1. Get started.
Before you start work with Kubernetes you need to install:  
Azure cli - https://docs.microsoft.com/en-us/cli/azure/install-azure-cli  
Kubectl:  
  `az aks install-cli`

# 2. How to login to aks cluster.
  Login to the azure infrastructure:  
  `az login
  az account set --subscription "Microsoft Azure Enterprise MSDN Dev/Test"`  
  Download AKS credentials:  
  `az aks get-credentials --resource-group crgd3 --name crgd3-k8s-01`  
  Check access:  
  `kubectl get nodes`

# 3. How to open the Kubernetes dashboard.
  `az aks browse --resource-group crgd3 --name crgd3-k8s-01`  
  Use kubeconfig authentication to login.  
  By default az aks get-credentials command downloads config to C:\Users\UserName\.kube\config  

