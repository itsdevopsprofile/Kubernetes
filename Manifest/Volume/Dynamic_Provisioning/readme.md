# Installing AWS EBS CSI Driver with Dynamic Provisioning of EBS Volumes


## Prerequisites
- A running Kubernetes cluster.
- An AWS account with access to create an IAM user and obtain an access key and secret key.

## Installing Helm
Helm is a package manager for Kubernetes that simplifies the deployment and management of applications.

- Run the following commands to install Helm
```
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
chmod 700 get_helm.sh
./get_helm.sh
```

## Installing AWS EBS CSI Driver
- Create a secret to store your AWS access key and secret key using the following command:
```
kubectl create secret generic aws-secret \
    --namespace kube-system \
    --from-literal "key_id=${AWS_ACCESS_KEY_ID}" \
    --from-literal "access_key=${AWS_SECRET_ACCESS_KEY}"
```

- Add the AWS EBS CSI Driver Helm chart repository:
```
helm repo add aws-ebs-csi-driver https://kubernetes-sigs.github.io/aws-ebs-csi-driver
helm repo update
```

- Deploy the AWS EBS CSI Driver using the following command:
```
helm upgrade --install aws-ebs-csi-driver \
    --namespace kube-system \
    aws-ebs-csi-driver/aws-ebs-csi-driver
```

- Verify that the driver has been deployed and the pods are running:
```
kubectl get pods -n kube-system -l app.kubernetes.io/name=aws-ebs-csi-driver
```

## Provisioning EBS Volumes
- Create a storageclass.yaml file and apply the storageclass.yaml file using the following command:
```
kubectl apply -f storageclass.yaml
```

- Create a pvc.yaml file and apply the pvc.yaml file using the following command:
```
kubectl apply -f pvc.yaml
```

- Create a pod.yaml file and apply the pod.yaml file using the following command:
```
kubectl apply -f pod.yaml
```

- Verify that the EBS volume has been provisioned and attached to the pod:
```
kubectl exec -it app -- df -h /data
```
The output of the above command should show the mounted EBS volume and its available disk space.

