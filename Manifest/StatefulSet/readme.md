<img width="1125" height="333" alt="image" src="https://github.com/user-attachments/assets/617391bf-3e52-4866-829e-aa6756376f0d" />




````
apiVersion: apps/v1
kind: StatefulSet
metadata: 
  name: redis
spec:
  serviceName: "redis"
  replicas: 2
  selector:
    matchLabels:
      app: demo 
  template:
    metadata:
      name: tmp-1
      labels:
        app: demo
    spec:
      containers:
        - name: redis 
          image: redis:5.0.5
          ports:
          - containerPort: 6379
            name: redis
  volumeClaimTemplates:
  - metadata:
      name: redis-data
    spec:
      accessModes: ["ReadWriteOnce"]
      resources:
        requests:
          storage: 1Gi
````
````
kubectl apply -f sts.yaml
````
````
kubectl get sts
````
