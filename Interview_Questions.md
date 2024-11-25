## Basic EKS Interview Questions

What is Amazon EKS, and why is it used?

EKS is a managed Kubernetes service provided by AWS. It allows users to run Kubernetes without having to install, manage, and operate Kubernetes control planes or nodes.

What are the main components of EKS?

The primary components include the control plane (AWS-managed) and worker nodes (user-managed or self-managed). The control plane consists of the API server, etcd, and core Kubernetes controllers, while worker nodes are EC2 instances or Fargate instances that run your workloads.

How does EKS differ from ECS?

EKS uses Kubernetes as the orchestration engine, which is open-source, whereas ECS is AWS’s own proprietary container orchestration service. EKS offers more flexibility and is ideal for multi-cloud setups, whereas ECS is more tightly integrated with AWS.

What is the role of IAM in EKS?

IAM (Identity and Access Management) is used for controlling access to AWS resources. In EKS, IAM roles are used to control which users and services can interact with the EKS cluster.

Explain node groups in EKS.

Node groups in EKS are collections of EC2 instances that function as worker nodes. Managed node groups allow you to automatically provision and manage EC2 instances, making it easier to run and manage Kubernetes applications.

What are the different deployment options for EKS nodes?

EKS nodes can be deployed on EC2 instances (self-managed or in managed node groups) or on AWS Fargate, which is a serverless compute option that allows Kubernetes pods to run without managing the underlying instances.

## Intermediate EKS Interview Questions

How do you configure networking in an EKS cluster?

EKS networking can be configured using VPC CNI plugin for Kubernetes, which allows Kubernetes pods to have IP addresses in your VPC. You also configure security groups, NACLs, and subnet configurations for networking security and accessibility.

Explain the purpose of Cluster Autoscaler in EKS.

The Cluster Autoscaler automatically adjusts the size of the cluster, scaling up or down based on resource demand. It helps ensure optimal resource utilization by adding nodes when more resources are needed or removing nodes when resources are underutilized.

What is the AWS VPC CNI plugin, and why is it used?

The AWS VPC CNI plugin assigns VPC IPs to Kubernetes pods, enabling them to communicate directly with other resources within the VPC. It allows seamless integration of Kubernetes networking with the AWS networking stack.

How do you manage storage in EKS?

Storage in EKS can be managed using Amazon EBS (Elastic Block Store) for persistent volumes, Amazon EFS (Elastic File System) for shared file storage, and S3 for object storage. Kubernetes Persistent Volumes (PVs) and Persistent Volume Claims (PVCs) are used to manage storage.

Describe the process of setting up a new EKS cluster.

Setting up a new EKS cluster involves creating the cluster via the AWS Console, CLI, or SDK, configuring VPC and subnet requirements, adding worker nodes (managed node groups or self-managed EC2 instances), and setting up IAM roles and permissions for Kubernetes and user access.

## Advanced EKS Interview Questions

What are pod security policies, and how do they work in EKS?

Pod Security Policies (PSPs) are Kubernetes policies that define the security configurations a pod must adhere to in order to be accepted by the Kubernetes cluster. In EKS, PSPs can be enabled to control security-sensitive configurations such as privilege levels, host network access, and volume types.

How does EKS handle multi-AZ deployments?

EKS distributes the control plane across three availability zones by default, ensuring high availability. Worker nodes can be deployed in multiple AZs, providing fault tolerance and failover for workloads.

What is Karpenter, and how does it differ from the Cluster Autoscaler?

Karpenter is an open-source, flexible, high-performance Kubernetes cluster autoscaler, designed to provision just the right compute resources needed for workloads. Unlike the traditional Cluster Autoscaler, Karpenter considers custom constraints, such as availability zones and instance types.

Explain how you would troubleshoot an EKS node in a NotReady state.

Troubleshooting involves checking the node’s health status, inspecting logs, ensuring network configuration, verifying IAM role permissions, and ensuring the control plane connectivity to the worker node. Commands like kubectl describe node <node-name> can help identify issues with resources, networking, or configurations.

How can you secure an EKS cluster?

To secure an EKS cluster, you can:

Use IAM roles for limiting access to resources.

Implement Kubernetes RBAC (Role-Based Access Control) for granular permissions within the cluster.

Enable network policies to control pod-to-pod and pod-to-service communication.

Use security groups and VPC NACLs for network security.

Regularly update clusters to the latest Kubernetes version to patch vulnerabilities.

What is the EKS control plane logging feature?

EKS control plane logging allows logging of Kubernetes API, audit, authenticator, controller manager, and scheduler logs to CloudWatch, aiding in troubleshooting and monitoring.

How would you implement custom metrics in an EKS cluster?

Custom metrics can be implemented using Prometheus and Grafana for monitoring. You can use CloudWatch Container Insights to monitor your EKS cluster, or implement custom exporters to track application-specific metrics.

How does EKS integrate with CI/CD pipelines?

EKS integrates with CI/CD pipelines by using CodePipeline and CodeBuild for deployment, or other third-party CI/CD tools like Jenkins and GitLab CI. Continuous integration builds the Docker images and pushes them to ECR (Elastic Container Registry), and continuous deployment automates rolling out new pods or versions to the EKS cluster.

Preparing for EKS interviews involves a good understanding of Kubernetes concepts, AWS integrations, and cloud networking. These questions cover a range of foundational, intermediate, and advanced knowledge areas that will be beneficial for an EKS-related role.v
