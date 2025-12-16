# ReplicationController
````
apiVersion: v1
kind: ReplicationController
metadata:
  name: rc-nginx
spec:
  replicas: 3
  selector:
    app: nginxapp
  template:
    metadata:
      name: tmp-nginx
      labels:
        app: nginxapp
    spec:
      containers:
        - name: c1 
          image: nginx
````
````
kubectl apply -f rc.yaml
````
````
kubectl get rc
````
````
kubectl get pods
````
````
kubectl delete pod <podname>
````
````
kubectl get pods
````
# ReplicaSet
````
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: rs-nginx
spec:
  replicas: 3
  selector:
   matchlabels:
    app: nginxapp
   template:
    metadata:
      name: tmp-nginx
      labels:
        app: nginxapp
    spec:
      containers:
        - name: c1 
          image: nginx 
````



## Que. Diff RS & RC  ?
