## Pods 
are the smallest deployable units of computing that you can create and manage in Kubernetes.
A Pod (as in a pod of whales or pea pod) is a group of one or more containers

````
apiVersion: v1
kind: Pod
metadata:
  name: first-pod
  labels:
    env: dev
spec:
  containers:
    - name: c1 
      image: nginx
---
apiVersion: v1
kind: Service
metadata:
  name: svc-first-pod
spec:
  selector: 
    env: dev
  ports:
    - protocol: "TCP"
      port: 80
      targetPort: 80
  type: NodePort
````
````
kubectl apply -f pod.yaml
````
````
kubectl get pods
````
````
kubectl get svc
````

