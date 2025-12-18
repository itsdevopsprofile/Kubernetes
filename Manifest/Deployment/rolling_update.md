
````
apiVersion: apps/v1 
kind: Deployment
metadata: 
  name: mydeploy

spec: 
  replicas: 1
  selector: 
   matchLabels:
     env: dev

  template: 
   metadata:
      name: tmp-1
      labels:
        env: dev

   spec: 
     containers:
      - name: c1
        image: devopsprofile/app1
        ports:
        - containerPort: 80
---
apiVersion: v1 
kind: Service 
metadata:
  name: svc-mydeploy
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
kubectl get deploy -o wide
````
````
kubectl get svc
````

## Rolling Update
- switch to newer version
````
kubectl get deploy -o wide
````
````
kubectl set image deploy/mydeploy  c1=devopsprofile/app2 --record
````
````
kubectl rollout history deploy/mydeploy
````


## rollback to previous version
````
kubectl rollout undo deploy/mydeploy
````
---
