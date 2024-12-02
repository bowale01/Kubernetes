# Kubernetes


https://github.com/bregman-arie/devops-exercises/blob/master/topics/kubernetes/README.md



![image](https://github.com/bowale01/Kubernetes/assets/37187773/1b3dac71-1a04-4751-938c-69c55b205585)

source :- https://kubernetes.io/docs/concepts/architecture/    
          https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#autoscale


![image](https://github.com/user-attachments/assets/4f66e891-4a15-4589-bf87-95ba75df2f5c)



The architecture of Amazon Elastic Kubernetes Service (EKS) involves several components that work together to provide a managed Kubernetes environment. Here's an overview of the EKS architecture:

 Control Plane:
The control plane is the heart of the EKS architecture. It is responsible for managing and orchestrating the Kubernetes cluster. Amazon EKS provides a fully managed control plane, which eliminates the operational overhead of managing it yours

elf. The control plane runs across multiple availability zones for high availability and fault tolerance.

Amazon EKS API Server:
The EKS API server provides the interface for managing and interacting with the Kubernetes cluster. It handles requests and communicates with the underlying control plane components to perform cluster management tasks.

etcd:
etcd is a distributed key-value store that acts as the Kubernetes cluster's primary data store. It stores cluster state information, configuration data, and other metadata. Amazon EKS manages the etcd cluster for you, ensuring data durability and availability.

Worker Nodes:
Worker nodes are the compute instances that run your applications and services within the Kubernetes cluster. These nodes are responsible for executing the workloads and communicating with the control plane. Amazon EKS supports several types of Amazon EC2 instances as worker nodes, providing flexibility in terms of compute resources.

kubelet:
The kubelet is an agent that runs on each worker node. It is responsible for managing the containers and interacting with the control plane components. The kubelet receives instructions from the control plane and ensures that the desired state of the containers matches the actual state.

AWS Identity and Access Management (IAM):
IAM is used for authentication and authorization within EKS. It allows you to manage access to your Kubernetes resources by defining roles, users, and policies. IAM roles are associated with worker nodes, enabling them to interact with AWS services and resources securely.

VPC Networking:
EKS leverages Amazon Virtual Private Cloud (VPC) for networking. Each EKS cluster is associated with a VPC, which provides isolation, security, and connectivity for the cluster. Subnets, security groups, and other VPC components are used to define the network configuration for EKS.

Elastic Load Balancing (ELB):
EKS integrates with Elastic Load Balancing to distribute incoming traffic to the applications running within the cluster. You can use Application Load Balancers (ALB) or Network Load Balancers (NLB) to expose services externally or internally.

Auto Scaling:
EKS supports cluster auto scaling, which dynamically adjusts the number of worker nodes based on resource demands. You can define scaling policies and thresholds to ensure optimal utilization and availability of resources.

These are the key components and services that make up the EKS architecture. With EKS, you can focus on deploying and managing your applications while leveraging the scalability, availability, and automation provided by the AWS infrastructure and Kubernetes ecosystem
