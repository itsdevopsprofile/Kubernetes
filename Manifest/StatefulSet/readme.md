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
