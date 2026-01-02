

## 🔴 <span style="color:red">What is Kubernetes, and why is it important in the world of container orchestration?</span>

Kubernetes is an open-source container orchestration platform used to automate the deployment, scaling, and management of containerized applications.  
It is important because modern applications are built using microservices and containers, which need to run reliably across multiple machines. Kubernetes handles container scheduling, networking, scaling, and failure recovery automatically, making applications highly available and production-ready.

---

## 🔴 <span style="color:red">Explain the key components of Kubernetes and their roles in container management.</span>

Kubernetes has control plane and worker node components:

- **API Server** – Central entry point for all cluster operations  
- **etcd** – Distributed key-value store that holds cluster state  
- **Scheduler** – Decides which node a Pod should run on  
- **Controller Manager** – Ensures the cluster matches the desired state  
- **kubelet** – Runs on each node and manages Pods  
- **kube-proxy** – Handles networking and service traffic  

Together, these components manage container lifecycle and cluster stability.

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

## 🔴 <span style="color:red">Describe
