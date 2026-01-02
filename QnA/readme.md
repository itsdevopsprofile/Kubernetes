
## 🔴 <span style="color:red">What is Kubernetes, and why is it important in the world of container orchestration?</span>

Kubernetes is an open-source container orchestration platform that automates deployment, scaling, and management of containerized applications.  
It is important because modern applications run many containers across multiple machines, and Kubernetes manages them efficiently with high availability and self-healing.

---

## 🔴 <span style="color:red">Explain the key components of Kubernetes and their roles in container management.</span>

- API Server – Entry point for all cluster operations  
- etcd – Stores cluster state  
- Scheduler – Assigns Pods to nodes  
- Controller Manager – Maintains desired state  
- kubelet – Runs Pods on nodes  
- kube-proxy – Handles networking and traffic routing  

---

## 🔴 <span style="color:red">How do you deploy a containerized application on a Kubernetes cluster? Walk me through the process.</span>

1. Create a Docker image  
2. Push image to a container registry  
3. Write Kubernetes YAML (Deployment, Service)  
4. Apply manifests using kubectl  
5. Verify Pods and Services  

---

## 🔴 <span style="color:red">Describe Kubernetes Deployments and StatefulSets. What are the differences, and when would you use one over the other?</span>

Deployment is used for stateless applications with interchangeable Pods.  
StatefulSet is used for stateful applications that need stable identity and persistent storage, such as databases.

---

## 🔴 <span style="color:red">How does Kubernetes handle load balancing for containerized applications?</span>

Kubernetes uses Services to distribute traffic across Pods.  
For external traffic, it uses NodePort, LoadBalancer, or Ingress controllers.

---

## 🔴 <span style="color:red">What is a Kubernetes Namespace, and why would you use multiple namespaces in a cluster?</span>

Namespaces logically isolate resources within a cluster.  
They are used for environment separation, access control, and resource management.

---

## 🔴 <span style="color:red">Explain the concept of Kubernetes Services and how they enable network connectivity for Pods.</span>

Services provide a stable IP and DNS name to access Pods.  
They enable load balancing and service discovery even when Pods are recreated.

---

## 🔴 <span style="color:red">What is the role of a Kubernetes Ingress controller, and how does it work?</span>

An Ingress controller manages HTTP/HTTPS traffic routing based on hostnames and paths.  
It acts as a Layer 7 load balancer for applications.

---

## 🔴 <span style="color:red">What is Kubernetes' role in auto-scaling, and how can you set up Horizontal Pod Autoscaling (HPA)?</span>

Kubernetes supports auto-scaling using HPA, which scales Pods based on metrics like CPU or memory.  
It requires Metrics Server or Prometheus Adapter.

---

## 🔴 <span style="color:red">Describe Kubernetes rolling updates and canary deployments. When and why would you use each approach?</span>

Rolling updates replace Pods gradually with zero downtime.  
Canary deployments release a new version to a small user group to reduce risk.

---

## 🔴 <span style="color:red">Explain Kubernetes' role in self-healing and how it handles container failures.</span>

Kubernetes automatically restarts failed containers, reschedules Pods, and maintains the desired replica count using controllers.

---

## 🔴 <span style="color:red">What are Kubernetes ConfigMaps and Secrets, and how do they differ in terms of storing configuration data?</span>

ConfigMaps store non-sensitive data.  
Secrets store sensitive data like passwords and tokens (base64 encoded).

---

## 🔴 <span style="color:red">How would you upgrade a Kubernetes cluster to a new version while minimizing downtime?</span>

By upgrading control plane components first, then worker nodes gradually using rolling upgrades while ensuring application replicas remain available.

---

## 🔴 <span style="color:red">What is a Helm chart, and how does it simplify application deployment on Kubernetes?</span>

Helm is a package manager for Kubernetes.  
Helm charts bundle application manifests, making deployments reusable, versioned, and configurable.

---

## 🔴 <span style="color:red">How do you monitor a Kubernetes cluster and its workloads?</span>

Using tools like Prometheus for metrics, Grafana for visualization, and Fluentd or Loki for logging.

---

## 🔴 <span style="color:red">Explain Kubernetes RBAC (Role-Based Access Control) and how you would configure it to secure your cluster.</span>

RBAC defines who can access which resources.  
It uses Roles, ClusterRoles, RoleBindings, and Service Accounts to enforce least privilege.

---

## 🔴 <span style="color:red">Describe the concept of Immutable Infrastructure and how it relates to Kubernetes.</span>

Infrastructure is not modified after deployment.  
In Kubernetes, updates are done by replacing Pods instead of changing running ones.

---

## 🔴 <span style="color:red">How do you handle secrets rotation for applications running in Kubernetes, and why is it important?</span>

Secrets rotation can be handled using external secret managers and rolling Pod restarts.  
It improves security by reducing credential exposure.

---

## 🔴 <span style="color:red">Discuss the challenges and best practices for running stateful applications in Kubernetes.</span>

Challenges include data persistence and backups.  
Best practices include using StatefulSets, persistent volumes, and regular backups.

---

## 🔴 <span style="color:red">Share an example of a complex Kubernetes project you've worked on.</span>

Example: Deploying a three-tier application with CI/CD, Ingress, auto-scaling, monitoring, and secure secret management while ensuring zero downtime deployments.

---

---

## 🔹 SCENARIO-BASED QUESTIONS

---

## 🔴 <span style="color:red">How would you design a highly available microservices architecture on Kubernetes?</span>

By using Deployments, Services, HPA, multiple replicas, readiness probes, and spreading Pods across nodes.

---

## 🔴 <span style="color:red">How would you perform a zero-downtime deployment?</span>

Using rolling updates or blue-green deployment with health checks and traffic switching.

---

## 🔴 <span style="color:red">How would you ensure data persistence and backups for a database running in Kubernetes?</span>

Using StatefulSets with persistent volumes and automated backup jobs.

---

## 🔴 <span style="color:red">How would you implement a multi-cluster Kubernetes strategy?</span>

Using centralized CI/CD, GitOps, service mesh, and federation tools for consistency.

---

## 🔴 <span style="color:red">How would you diagnose high resource usage in a Pod?</span>

By checking metrics, logs, resource limits, node pressure, and tuning CPU/memory requests.

---

## 🔴 <span style="color:red">How would you enable secure pod-to-pod communication?</span>

By implementing Network Policies and enforcing least-privileged communication paths.

---

## 🔴 <span style="color:red">How would you configure HPA for variable traffic?</span>

By defining CPU/memory thresholds and minimum/maximum replica limits.

---

## 🔴 <span style="color:red">Describe a GitOps workflow for Kubernetes.</span>

Changes are pushed to Git → CI validates → GitOps tool syncs cluster automatically.

---

## 🔴 <span style="color:red">How would you migrate a monolithic app to microservices on Kubernetes?</span>

By breaking services gradually, containerizing components, and deploying incrementally.

---

