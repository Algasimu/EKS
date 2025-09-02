# Install EKS

Please follow the prerequisites doc before this.

## Install using Fargate

```
eksctl create cluster --name demo-cluster --region us-east-1 --fargate
```

## Update the kubeconfig

```
aws eks update-kubeconfig --name test-cluster --region us-west-2
```

## Delete the cluster

```
eksctl delete cluster --name demo-cluster --region us-east-1
```


