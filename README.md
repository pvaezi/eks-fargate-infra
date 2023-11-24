# Deploy EKS Cluster on AWS Leveraging Fargate

This repository creates Kubernetes cluster on to AWS using only serverless tools, EKS for managing control plane, and Fargate for deploying containers in a fully serverless manner.

## Perquisites

1. Install AWS CLI
2. Install Kubectl CLI
3. Install terraform
4. Setup necessary IAM policies for terraform to be able to deploy EKS cluster.

## Infra Deployment

Select and modify respective terraform variable, below we have used `qa.tfvars`, then run below commands in the `terraform` folder:

```bash
terraform init
terraform validate
terraform apply -var-file=qa.tfvars
```

Get kube config for the cluster you created:

```bash
aws eks update-kubeconfig --name main-qa --region us-east-2
kubectl get pods -A
```

You should see pods running.
