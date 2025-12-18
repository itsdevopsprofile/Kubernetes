# blue.yaml
````
apiVersion: apps/v1
kind: Deployment
metadata: 
  name: blue-dep 
spec:
  replicas: 1
  selector:
    matchLabels:
      app: blue
  template: 
    metadata:
      name: tmp-01
      labels:
        app: blue
    spec:
      containers:
        - name: c1 
          image: devopsprofile/app1
          ports:
            - containerPort: 80

````
# green.yaml
````
apiVersion: apps/v1
kind: Deployment
metadata: 
  name: green-dep
spec:
  replicas: 1
  selector:
    matchLabels:
      app: green
  template: 
    metadata:
      name: tmp-01
      labels:
        app: green
    spec:
      containers:
        - name: c1 
          image: devopsprofile/app2
          ports:
            - containerPort: 80
````
# service.yaml
````
apiVersion: v1
kind: Service
metadata:
 name: test-app-svc
spec:
  selector:
    app: blue
  ports:
    - protocol: "TCP"
      port: 80
      targetPort: 80
  type: NodePort
````

### switch traffic from blue to green
- edit service.yaml
- change selector from blue to green
