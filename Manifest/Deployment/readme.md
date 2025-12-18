
**Kubernetes Deployment** is an object that helps you **run and manage your application automatically**.

It:

* Runs **multiple copies (replicas)** of your app
* **Restarts pods** if they crash (self-healing)
* **Scales up/down** easily
* Updates the app **without downtime** (rolling updates)


```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: netflix
spec:
  replicas: 3
  selector:
    matchLabels:
        app: netflix
  template:
    metadata:
      name: tmp-01
      labels:
         app: netflix
    spec:
      containers:
         - name: super-mario
           image: devopsprofile/netflix
           ports:
             - containerPort: 80
---
apiVersion: v1
kind: Service
metadata:
  name: svc-netflix
spec:
 selector:
    app: netflix
 ports:
   - port: 80
     targetPort: 80
     protocol: "TCP"
 type: NodePort
 ```

#### Commands:
````
kubectl apply -f dep.yaml
````
````
kubectl get deploy
````
````
kubectl get svc
````
