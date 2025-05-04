```
# AWS Infrastructure Provisioning with Crossplane and Kubernetes

This project provisions a complete AWS infrastructure stack — including an S3 bucket, VPC, and EKS cluster — using [Crossplane](https://crossplane.io/) from within a local Kubernetes cluster running on Minikube.

## 📌 Features

- Local Kubernetes setup via Minikube
- Crossplane installed using Helm
- AWS S3 bucket with versioning enabled
- VPC with:
  - Public and private subnets in multiple AZs
  - NAT Gateway + Internet Gateway
  - Elastic IPs and custom route tables
- EKS Cluster provisioned via Crossplane’s AWS provider
- IAM roles and OIDC setup for secure Kubernetes-to-AWS integration

## 📦 Tech Stack

- Kubernetes (Minikube)
- Crossplane
- Helm
- AWS (VPC, EKS, IAM, S3)
- YAML (K8s manifests)

## 🛠 Folder Structure

```bash
.
├── aws-credentials.txt
├── crossplane
│   ├── provider-aws-config.yaml
│   ├── provider-aws-ec2.yaml
│   ├── provider-aws-eks.yaml
│   ├── provider-aws-iam.yaml
│   └── provider-aws-s3.yaml
├── eks
│   ├── eks-iam-role.yaml
│   ├── eks.yaml
│   ├── nodes-iam.yaml
│   └── nodes.yaml
├── readme.MD
├── s3
│   ├── bucket-versioning.yaml
│   └── my-bucket.yaml
└── vpc
    ├── igw.yaml
    ├── nat.yaml
    ├── routes.yaml
    ├── subnets.yaml
    └── vpc.yaml
```

## 📸 Screenshots

![VPC Architecture Screenshot](./assets/vpc-screenshot.png)

## 🚀 Getting Started

1. Set up Minikube and Helm
2. Clone this repository
3. Configure AWS credentials as a Kubernetes Secret
4. Apply the manifests in order using `kubectl apply -f`

> Note: This setup is designed for learning/demo purposes and uses hardcoded values. For production, consider using Crossplane Compositions and Kustomize.

## 🧠 Learnings

This project helped me:
- Understand Kubernetes-native Infrastructure as Code
- Work with Crossplane’s reconciliation model
- Explore AWS resource provisioning without leaving K8s

## 📎 References

- [Crossplane Documentation](https://docs.crossplane.io/)
- [AWS Crossplane Providers](https://marketplace.upbound.io/providers)

---

## 💬 Feedback

Feel free to open issues or connect if you're working on something similar!
```
