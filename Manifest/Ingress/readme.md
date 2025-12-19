# ✅ Install Helm on **Ubuntu**

### 1️⃣ Update packages

```bash
sudo apt update
```

---

### 2️⃣ Install required tools

```bash
sudo apt install -y curl apt-transport-https
```

---

### 3️⃣ Download & install Helm

```bash
curl -fsSL https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash
```

---

### 4️⃣ Verify Helm installation

```bash
helm version
```

# ✅ After Helm is Installed → Install NGINX Ingress Controller

```bash
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update
```

```bash
helm install ingress-nginx ingress-nginx/ingress-nginx \
  --namespace ingress-nginx \
  --create-namespace \
  --set controller.service.type=LoadBalancer
```

---

# ✅ Verify Everything

```bash
kubectl get pods -n ingress-nginx
kubectl get svc -n ingress-nginx
```

Look for:

```
ingress-nginx-controller   Running
EXTERNAL-IP: <AWS-ELB-DNS>
```

---

# 🌍 Access Your App

```bash
http://<AWS-LOAD-BALANCER-DNS>/
http://<AWS-LOAD-BALANCER-DNS>/tea
```

---

If you hit **any error**, copy-paste the error here and I’ll fix it with you step by step 💪
