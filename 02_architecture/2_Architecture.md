# K8s architecture with a company analogy

Imagine a big IT company where different teams and employees work together to complete tasks.

In the same way, Kubernetes also has different components that work together to deploy and manage applications.

1. kubectl → CEO of the Company
    
    kubectl acts like the CEO. The CEO gives instructions to management rather than directly doing the work.
    
    Example:
    
    ```groovy[9966eb38-8f1c-4c15-9852-740804441578_2_Architecture.pdf](../../../Music/9966eb38-8f1c-4c15-9852-740804441578_2_Architecture.pdf)
    kubectl create deployment nginx --image=nginx
    ```
    
2. API Server → Senior Manager / Reception Desk
    
    The API Server is like the Senior Manager or Reception Desk.
    
    All requests first come here.
    
    Responsibilities:
    
    - Receives requests
    - Validates requests
    - Sends requests to correct components
    - Acts as communication hub
3. Sheduler → HR Team
    
    Scheduler works like HR.
    
    It decides which Node has enough CPU and Memory to run Pods.
    
4. Node → Branch Office
    
    A Node is like a branch office where employees actually work.
    
    Pods run inside Nodes.
    
5. Kubelet → Office Administrator
    
    Kubelet acts like the Office Administrator.
    
    Responsibilities:
    
    - Receives instructions from API Server
    - Creates Pods
    - Monitors Pod health
    - Sends status updates
    
6. Container Runtime → Interviewer / Hiring Team
    
    Container Runtime actually creates containers.
    
    Examples:
    
    - containerd
    - CRI-O
    - Docker
    
    Analogy:
    
    Resume = Docker Image
    
    Employee Creation = Container Creation
    
7. POD → Employee
    
    Pod is like an employee.
    
    Inside the Pod, actual work happens.
    
8. ETCD → Accounts Team / Company Database
    
    ETCD stores all cluster information:
    
    - Pod details
    - Node details
    - Configurations
    - Secrets
    - Desired State
    
9. Controller Manager → Auditor / Client Representative
    
    Controller Manager ensures Current State always matches Desired State.
    
    Example:
    
    Desired State = 2 Pods
    
    Current State = 1 Pod
    

Controller Manager notices mismatch and recreates missing Pod.

Complete Flow:

1. kubectl sends request

2. API Server receives request

3. Scheduler selects Node

4. API Server informs Kubelet

5. Kubelet talks to Container Runtime

6. Pod gets created

7. Kubelet sends health updates

8. Controller Manager ensures desired state

## Complete Flow:

1. Kubectl sends request
2. API Server receives request
3. Scheduler selects Node
4. API Server informs Kubelet
5. Kubelet talks to Container Runtime
6. Pod gets created
7. Kubelet sends health updates
8. Controller Manager ensures desired state

## Mapping Table:

kubectl = CEO

API Server = Senior Manager

Scheduler = HR Team

Node = Branch Office

Kubelet = Office Administrator

Container Runtime = Interviewer

Pod = Employee

ETCD = Accounts Team

Controller Manager = Auditor

## One-line Summary:

k8s works like a smart company where every team has a responsibility, and all teams coordinate together to ensure applications are always running properly.