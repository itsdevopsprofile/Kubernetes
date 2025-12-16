# Kubernetes Basic Commands

### 🔹 **Check Nodes**

```bash
kubectl get nodes
```

✅ Shows all present nodes.

---

### 🔹 **Create Pod Using Command**

```bash
kubectl run pod-1 --image=nginx
```

✅ Creates a pod named **pod-1** with nginx.

---

### 🔹 **List Pods**

```bash
kubectl get pods
```

✅ Shows all running pods.

---

### 🔹 **Expose Pod To Access Application(Create Service Using Command)**



Types of Services:
1. ClusterIP
2. NodePort (30000-32767)
3. LoadBalancer


## ✅ **ClusterIP (Internal Access Only)**

```bash
kubectl expose pod pod-1 --port=80 --target-port=80 --type=ClusterIP
```
```
kubectl get svc
```

---

## ✅ **NodePort (Access from Browser using Node IP)**

```bash
kubectl expose pod pod-1 --port=80 --target-port=80 --type=NodePort
```
```
kubectl get svc
```

Access:

```text
http://<Node-IP>:<NodePort>
```

---
<img width="681" height="306" alt="image" src="https://github.com/user-attachments/assets/405e5f43-7f7f-457d-bbba-a32e34f7dd90" />
