## Create EKS Cluster
- prerequisites:
  1. ec2 instance
  2. eksctl
  3. kubectl
  4. aws cli
     
**1:Install eksctl CLI tool for creating EKS Clusters on AWS**
````
curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
````

````
sudo mv /tmp/eksctl /usr/local/bin
```` 

```` 
eksctl version
````

**2:Install kubectl**

````
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
````
````
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
````
````
chmod +x kubectl
mkdir -p ~/.local/bin
mv ./kubectl ~/.local/bin/kubectl
````
````
kubectl version --client
````

**3:Install AWS CLI on Ubuntu**
````
sudo apt install unzip -y
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
````


**4:Configure AWS CLI**
````
aws configure
````

**5:Create Amazon EKS cluster using eksctl**
````
eksctl create cluster --name dev-ekscluster --region ap-southeast-1 --version 1.32 --nodegroup-name linux-nodes --node-type t2.medium --nodes 2
````
**6: Log In Into EKS cluster**
````
aws eks update-kubeconfig --name dev-ekscluster
````
**7: Delete EKS Cluster**
````
eksctl delete cluster --name dev-ekscluster --region ap-southeast-1
````
