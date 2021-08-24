# EKS Quickstart

This will install an EKS cluster using eksctl, configure cluster services using flux, and deploy some sample applications.


## Prerequisites

[eksctl](https://eksctl.io/introduction/#installation) – A command line tool for working with EKS clusters that automates many individual tasks. This guide requires that you use version 0.62.0 or later. For more information, see The eksctl command line utility.

[kubectl](https://kubernetes.io/docs/tasks/tools/) – A command line tool for working with Kubernetes clusters. 

[fluxctl](https://www.weave.works/oss/flux/) - a command-line tool that can talk to Weave Flux - it makes it very easy to manage, automate and even roll back deployments.

[IAM policies](https://eksctl.io/usage/iam-policies/) for:

- ALB Ingress
- auto-scaler
- CloudWatch

## Cluster Components

- [ALB ingress controller](https://github.com/kubernetes-sigs/aws-alb-ingress-controller) -- to easily expose services to the World.
- [Cluster autoscaler](https://github.com/kubernetes/autoscaler/tree/master/cluster-autoscaler) -- to [automatically add/remove nodes](https://aws.amazon.com/premiumsupport/knowledge-center/eks-cluster-autoscaler-setup/) to/from your cluster based on its usage.
- Jenkins -- configured using the [Jenkins Operator](https://github.com/jenkinsci/kubernetes-operator).
- [Sysdig Agent](https://docs.sysdig.com/en/sysdig-agent.html)

## Executing the playbook
```
ansible-playbooks -v quickstart.yml -e eks_cluster_name=eks-sysdig -e sysdig_key="<key_value>"
```