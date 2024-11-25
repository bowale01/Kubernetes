# Basic EKS Interview Questions

### What is Amazon EKS, and why is it used?

EKS is a managed Kubernetes service provided by AWS. It allows users to run Kubernetes without having to install, manage, and operate Kubernetes control planes or nodes.

### What are the main components of EKS?

The primary components include the control plane (AWS-managed) and worker nodes (user-managed or self-managed). The control plane consists of the API server, etcd, and core Kubernetes controllers, while worker nodes are EC2 instances or Fargate instances that run your workloads.

### How does EKS differ from ECS?

EKS uses Kubernetes as the orchestration engine, which is open-source, whereas ECS is AWS’s own proprietary container orchestration service. EKS offers more flexibility and is ideal for multi-cloud setups, whereas ECS is more tightly integrated with AWS.

### What is the role of IAM in EKS?

IAM (Identity and Access Management) is used for controlling access to AWS resources. In EKS, IAM roles are used to control which users and services can interact with the EKS cluster.

### Explain node groups in EKS.

Node groups in EKS are collections of EC2 instances that function as worker nodes. Managed node groups allow you to automatically provision and manage EC2 instances, making it easier to run and manage Kubernetes applications.

### What are the different deployment options for EKS nodes?

EKS nodes can be deployed on EC2 instances (self-managed or in managed node groups) or on AWS Fargate, which is a serverless compute option that allows Kubernetes pods to run without managing the underlying instances.

# Intermediate EKS Interview Questions

### How do you configure networking in an EKS cluster?

EKS networking can be configured using VPC CNI plugin for Kubernetes, which allows Kubernetes pods to have IP addresses in your VPC. You also configure security groups, NACLs, and subnet configurations for networking security and accessibility.

### Explain the purpose of Cluster Autoscaler in EKS.

The Cluster Autoscaler automatically adjusts the size of the cluster, scaling up or down based on resource demand. It helps ensure optimal resource utilization by adding nodes when more resources are needed or removing nodes when resources are underutilized.

### What is the AWS VPC CNI plugin, and why is it used?

The AWS VPC CNI plugin assigns VPC IPs to Kubernetes pods, enabling them to communicate directly with other resources within the VPC. It allows seamless integration of Kubernetes networking with the AWS networking stack.

### How do you manage storage in EKS?

Storage in EKS can be managed using Amazon EBS (Elastic Block Store) for persistent volumes, Amazon EFS (Elastic File System) for shared file storage, and S3 for object storage. Kubernetes Persistent Volumes (PVs) and Persistent Volume Claims (PVCs) are used to manage storage.

### Describe the process of setting up a new EKS cluster.

Setting up a new EKS cluster involves creating the cluster via the AWS Console, CLI, or SDK, configuring VPC and subnet requirements, adding worker nodes (managed node groups or self-managed EC2 instances), and setting up IAM roles and permissions for Kubernetes and user access.

# Advanced EKS Interview Questions

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

Preparing for EKS interviews involves a good understanding of Kubernetes concepts, AWS integrations, and cloud networking. These questions cover a range of foundational, intermediate, and advanced knowledge areas that will be beneficial for an EKS-related role.

Kubernetes Basics
What is Kubernetes, and what are its key components?
Key components: API Server, Scheduler, Controller Manager, Kubelet, Kube-proxy, etc.
Explain the role of Pods, Deployments, Services, and ConfigMaps.
Pods: Smallest deployable unit in Kubernetes.
Deployments: Ensure the desired state of pods.
Services: Expose pods to the network.
ConfigMaps: Store configuration data as key-value pairs.
Containerization and Orchestration
What is the role of a container runtime in Kubernetes?
Container runtimes like Docker or containerd are responsible for running containers.
How does Kubernetes differ from traditional VMs or Docker Swarm?
Discuss orchestration, scalability, and declarative state management.
AWS Basics
What is Amazon EKS?
Fully managed Kubernetes service.
What are the advantages of using EKS compared to running Kubernetes on EC2?
Managed control plane, auto-scaling, and seamless AWS integration.
2. Intermediate Questions
These focus on EKS-specific integrations and operational concerns.

AWS EKS Integrations
How does EKS integrate with IAM?
IAM roles for service accounts (IRSA), which allow Kubernetes pods to use AWS resources securely.
What is the purpose of a VPC in EKS?
Isolation of cluster resources, pod-to-pod and pod-to-service communication via VPC CNI.
Networking in Kubernetes
Explain the Kubernetes networking model.
Every pod gets its own IP address; communication is direct and without NAT.
What is the role of a CNI plugin in EKS?
Amazon VPC CNI is used to assign IP addresses to pods from the VPC subnet.
EKS Deployment and Management
What tools would you use to deploy and manage Kubernetes applications?
Helm, kubectl, Kustomize.
How do you handle logging and monitoring in an EKS cluster?
CloudWatch Container Insights, FluentD, Prometheus, Grafana.
Security in EKS
What is the purpose of Kubernetes Network Policies?
Control traffic flow between pods and external services.
How do you implement secrets management in EKS?
Kubernetes Secrets, AWS Secrets Manager, or SSM Parameter Store.
3. Advanced Questions
These are scenario-based or related to best practices and troubleshooting.

Advanced Kubernetes Operations
How do you troubleshoot pods stuck in a "CrashLoopBackOff" state?
Check logs (kubectl logs), inspect events (kubectl describe pod), and ensure proper configurations.
How would you scale a Kubernetes cluster in EKS?
Use the Cluster Autoscaler to add or remove nodes based on workload demands.
Explain the difference between Horizontal Pod Autoscaler (HPA) and Vertical Pod Autoscaler (VPA).
HPA scales pods horizontally (number of pods); VPA adjusts resources (CPU/memory) vertically.
EKS Cost Optimization
What strategies would you use to optimize costs in an EKS cluster?
Right-size nodes, use Spot Instances, implement auto-scaling, and remove unused resources.
Multi-Cluster Management
How would you manage multiple EKS clusters across different regions?
Use tools like Rancher, ArgoCD, or AWS CloudFormation StackSets.
Disaster Recovery and High Availability
How do you ensure high availability in EKS?
Multi-AZ deployments, redundant control plane nodes, and regional replication.
What steps would you take for disaster recovery in EKS?
Backup etcd, use tools like Velero for backup and restore of Kubernetes resources.
Performance Tuning
How would you debug and resolve a Kubernetes API server bottleneck in EKS?
Check API server metrics, increase resource limits, optimize client-side retries, or offload workloads.
4. Cloud-Native Tooling Questions
These focus on integrating Kubernetes with popular tools and AWS-native services.

CI/CD with Kubernetes
How would you implement CI/CD in an EKS environment?
Use GitOps tools like ArgoCD or FluxCD, or pipelines with Jenkins and AWS CodePipeline.
Monitoring and Observability
What tools would you use to monitor EKS?
Prometheus, Grafana, AWS CloudWatch, Datadog.
How do you collect and analyze logs in an EKS cluster?
FluentD/FluentBit for log forwarding, ELK stack for analysis.
Infrastructure as Code (IaC)
What IaC tools are commonly used for EKS?
AWS CloudFormation, Terraform, Pulumi.
How do you version control Kubernetes manifests?
Use Git with tools like Kustomize or Helm for templating.
5. Scenario-Based Questions
You notice high latency between pods in your EKS cluster. How do you troubleshoot?
Check the network policies, pod logs, and VPC CNI plugin status. Analyze CloudWatch metrics for network health.
A pod cannot access an S3 bucket. What do you check?
Verify IAM role for the pod, service account annotations, and network configurations.
How would you implement blue-green or canary deployments in EKS?
Use tools like Argo Rollouts or Istio for advanced traffic splitting.
Preparation Tips
Hands-On Practice:

Deploy sample applications in EKS.
Experiment with monitoring, scaling, and logging tools.
Documentation Familiarity:

Be well-versed in Kubernetes and AWS EKS documentation.
Real-World Scenarios:

Practice troubleshooting scenarios and multi-service setups.
By covering these areas, you will be well-prepared to answer both theoretical and practical questions during an EKS interview.
