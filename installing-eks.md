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

If you want to create the same EKS cluster with EC2 worker nodes instead of Fargate, you just need to drop the --fargate flag and specify node group options with --nodegroup-name, --node-type, and optionally scaling options.
Here’s an example command:

```
eksctl create cluster \
  --name demo-cluster \
  --region us-east-1 \
  --nodegroup-name demo-nodes \
  --node-type t3.medium \
  --nodes 2 \
  --nodes-min 1 \
  --nodes-max 3
```

By default, eksctl will provision EC2 nodes if you don’t use --fargate.
