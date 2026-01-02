
---

## 🔴 What is Kubernetes?

Kubernetes is an open-source container orchestration platform that automates deployment, scaling, networking, and self-healing of containerized applications across a cluster of machines.

---

## 🔴 Why is Kubernetes important?

Modern applications consist of many microservices running in containers. Kubernetes manages these containers efficiently by providing high availability, scalability, fault tolerance, and declarative infrastructure management.

---

## 🔴 What are the key features of Kubernetes?

- Automatic container scheduling  
- Self-healing (restart, reschedule)  
- Horizontal & vertical scaling  
- Service discovery & load balancing  
- Rolling updates & rollbacks  
- Configuration & secret management  
- Cloud-agnostic design  

---

## 🔴 What is Container Orchestration?

Container orchestration is the automated management of containerized applications, including deployment, networking, scaling, and lifecycle management. Kubernetes is the most widely used orchestration platform.

---

## 🔴 How are Docker and Kubernetes related?

Docker is used to build and package containers.  
Kubernetes is used to orchestrate and manage those containers at scale.

---


## 🔴 Explain Kubernetes architecture.

Kubernetes consists of a **control plane** and **worker nodes**.

### Control Plane:
- **kube-apiserver** – Central API interface  
- **etcd** – Stores cluster state  
- **kube-scheduler** – Assigns Pods to nodes  
- **controller-manager** – Maintains desired state  

### Worker Node:
- **kubelet** – Manages Pods on the node  
- **kube-proxy** – Handles networking and traffic routing  
- **Container Runtime** – Runs containers  

---

## 🔴 What is etcd?

etcd is a distributed key-value store that stores all cluster configuration and state data. It is the single source of truth for Kubernetes.

---

## 🔴 What is kubelet?

kubelet is an agent running on each worker node that ensures containers described in Pod specs are running and healthy.

---

## 🔴 What is kube-proxy?

kube-proxy manages networking rules that allow Services to route traffic to the correct Pods using iptables or eBPF.

---


---

## 🔴 What is a Pod?

A Pod is the smallest deployable unit in Kubernetes.  
It can contain one or more containers that share networking and storage.

---


## 🔴 What is a Deployment?

A Deployment manages stateless applications and provides:
- Replica management  
- Rolling updates  
- Rollbacks  

---

## 🔴 What is a StatefulSet?

StatefulSet is used for stateful applications such as databases.  
It provides:
- Stable Pod names  
- Persistent storage  
- Ordered deployment and scaling  

---

## 🔴 ReplicaSet vs ReplicationController?

ReplicaSet is the modern replacement for ReplicationController.  
It supports set-based selectors and is used internally by Deployments.

---

---

## 🔴 What is a Kubernetes Service?

A Service provides a stable IP and DNS name to expose a set of Pods and distribute traffic among them.

---

## 🔴 Types of Services?

- **ClusterIP** – Internal access  
- **NodePort** – External access via node  
- **LoadBalancer** – Cloud load balancer  

---

## 🔴 What is an Ingress?

Ingress manages external HTTP/HTTPS access and provides routing based on hostnames and paths using an Ingress Controller (NGINX, ALB, etc.).

---



---

## 🔴 ConfigMap vs Secret?

- **ConfigMap** – Non-sensitive configuration  
- **Secret** – Sensitive data (base64 encoded, can be encrypted at rest)

---

## 🔴 PersistentVolume (PV) vs PersistentVolumeClaim (PVC)?

- **PV** – Actual storage resource  
- **PVC** – Request for storage  


---

## 🔴 How does Kubernetes perform self-healing?

- Restarts failed containers  
- Reschedules Pods  
- Maintains desired replica count
---



---

## 🔴 <span style="color:red">How do you deploy a containerized application on a Kubernetes cluster? Walk me through the process.</span>

First, the application is containerized using Docker.  
The image is pushed to a container registry.  
Then Kubernetes manifests (Deployment, Service, ConfigMap, etc.) are written and applied using `kubectl`.  
Kubernetes schedules Pods, exposes them via Services, and continuously ensures the application is running as expected.

---

## 🔴 <span style="color:red">Describe Kubernetes Deployments and StatefulSets. What are the differences, and when would you use one over the other?</span>

Deployments are used for stateless applications where Pods are interchangeable, such as web applications.  
StatefulSets are used for stateful applications like databases, where stable Pod identity, storage, and ordering are required.  
If data persistence and stable networking are important, StatefulSet is preferred.

---

## 🔴 <span style="color:red">How does Kubernetes handle load balancing for containerized applications?</span>

Kubernetes uses Services to distribute traffic across multiple Pods.  
Internally, kube-proxy routes traffic using iptables or eBPF.  
For external access, Kubernetes supports NodePort, LoadBalancer, and Ingress-based load balancing.

---

## 🔴 <span style="color:red">What is a Kubernetes Namespace, and why would you use multiple namespaces in a cluster?</span>

A Namespace is a logical partition within a cluster.  
It is used to separate environments (dev, staging, prod), teams, or applications, and helps with access control, resource quotas, and organization.

---

## 🔴 <span style="color:red">Explain the concept of Kubernetes Services and how they enable network connectivity for Pods.</span>

Pods are ephemeral and their IPs change frequently.  
Services provide a stable IP and DNS name that routes traffic to matching Pods.  
This allows applications to communicate reliably without knowing Pod details.

---

## 🔴 <span style="color:red">What is the role of a Kubernetes Ingress controller, and how does it work?</span>

An Ingress controller manages external HTTP/HTTPS access to services.  
It routes traffic based on hostnames and URL paths and often provides TLS termination, authentication, and rate limiting.

---

## 🔴 <span style="color:red">What is Kubernetes' role in auto-scaling, and how can you set up Horizontal Pod Autoscaling (HPA)?</span>

Kubernetes supports auto-scaling through HPA, which adjusts the number of Pods based on metrics like CPU or memory usage.  
It requires a metrics provider such as Metrics Server or Prometheus.

---

## 🔴 <span style="color:red">Describe Kubernetes rolling updates and canary deployments. When and why would you use each approach?</span>

Rolling updates replace Pods gradually to avoid downtime.  
Canary deployments release a new version to a small subset of users to validate changes before full rollout.  
Canary is preferred when risk is high.

---

## 🔴 <span style="color:red">Explain Kubernetes' role in self-healing and how it handles container failures.</span>

Kubernetes continuously monitors Pods and nodes.  
If a container crashes, Kubernetes restarts it.  
If a Pod fails, a new one is created automatically to maintain the desired state.

---

## 🔴 <span style="color:red">What are Kubernetes ConfigMaps and Secrets, and how do they differ?</span>

ConfigMaps store non-sensitive configuration data such as URLs or feature flags.  
Secrets store sensitive data like passwords and tokens and are base64 encoded.

---

## 🔴 <span style="color:red">How would you upgrade a Kubernetes cluster to a new version while minimizing downtime?</span>

The control plane is upgraded first, followed by worker nodes in a rolling manner.  
Applications continue running using multiple replicas, ensuring no downtime.

---

## 🔴 <span style="color:red">What is a Helm chart, and how does it simplify application deployment?</span>

Helm is a Kubernetes package manager.  
Helm charts bundle Kubernetes manifests into reusable, configurable packages, making deployments consistent and easy to manage.

---

## 🔴 <span style="color:red">How do you monitor a Kubernetes cluster and its workloads?</span>

Monitoring is done using Prometheus for metrics, Grafana for dashboards, and tools like Fluentd or Loki for logs.  
Alerts are configured to detect failures early.

---

## 🔴 <span style="color:red">Explain Kubernetes RBAC and how you would configure it.</span>

RBAC controls access to cluster resources.  
Roles define permissions, and RoleBindings associate them with users or service accounts, following the principle of least privilege.

---

## 🔴 <span style="color:red">Describe Immutable Infrastructure and its relation to Kubernetes.</span>

Immutable Infrastructure means servers or containers are never modified after deployment.  
In Kubernetes, updates are done by replacing Pods, not changing running ones.

---

## 🔴 <span style="color:red">How do you handle secrets rotation in Kubernetes, and why is it important?</span>

Secrets are rotated using external secret managers and rolling Pod restarts.  
This reduces security risks caused by leaked or expired credentials.

---

## 🔴 <span style="color:red">Discuss challenges and best practices for running stateful applications in Kubernetes.</span>

Challenges include storage persistence, backups, and recovery.  
Best practices involve StatefulSets, persistent volumes, and scheduled backups.

---

## 🔴 <span style="color:red">Share an example of a complex Kubernetes project you've worked on.</span>

Example: Deploying a CI/CD-driven three-tier application with Ingress, HPA, monitoring, secret management, and rolling updates while maintaining high availability.

---

## 🔹 SCENARIO-BASED QUESTIONS

---

## 🔴 <span style="color:red">How would you design a highly available microservices architecture on Kubernetes?</span>

By deploying multiple replicas, using Services and Ingress, enabling HPA, implementing readiness probes, and distributing Pods across nodes.

---

## 🔴 <span style="color:red">How would you perform a zero-downtime deployment?</span>

By using rolling updates or blue-green deployments with health checks and controlled traffic switching.

---

## 🔴 <span style="color:red">How would you ensure data persistence and backups for a database?</span>

Using StatefulSets with persistent volumes and automated backup jobs or snapshots.

---

## 🔴 <span style="color:red">How would you implement a multi-cluster Kubernetes strategy?</span>

Using GitOps, centralized CI/CD pipelines, shared monitoring, and service mesh for cross-cluster communication.

---

## 🔴 <span style="color:red">How would you diagnose high resource usage in a Pod?</span>

By analyzing metrics, logs, resource limits, node pressure, and application behavior.

---

## 🔴 <span style="color:red">How would you enable secure pod-to-pod communication?</span>

By defining Network Policies that allow only required traffic paths.

---

## 🔴 <span style="color:red">How would you configure HPA for variable traffic?</span>

By setting CPU or memory thresholds along with minimum and maximum Pod limits.

---

## 🔴 <span style="color:red">Describe a GitOps workflow for Kubernetes.</span>

All configuration changes are pushed to Git.  
A GitOps tool automatically syncs the cluster with the repository state.

---


## 🔴 <span style="color:red">How would you optimize resource utilization in Kubernetes?</span>

By right-sizing requests and limits, enabling autoscaling, and removing unused workloads.

---


## 🔴 <span style="color:red">How would you ensure consistency in hybrid cloud Kubernetes?</span>

By standardizing configurations, using GitOps, and maintaining common tooling across clusters.

---

## 🔴 <span style="color:red">How would you troubleshoot a Kubernetes performance issue?</span>

By checking metrics, logs, events, node health, and application dependencies step by step.

---

