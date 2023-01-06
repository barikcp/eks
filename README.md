# EKS Cluster
Step-1: Create an EC2 instance.

Step-2: Connect EC2 instance from command prompt.

Step-3: Install "awscli"

       apt update
       apt install awscli
      
Step-4: Configure AWS

       aws configure
       
Step-5: Install Kubectl

        curl -O https://s3.us-west-2.amazonaws.com/amazon-eks/1.23.13/2022-10-31/bin/linux/amd64/kubectl
        openssl sha1 -sha256 kubectl
        chmod +x ./kubectl
        mkdir -p $HOME/bin && cp ./kubectl $HOME/bin/kubectl && export PATH=$PATH:$HOME/bin
        kubectl version --short --client
         
Step-6: Install eksctl

       curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
       sudo mv /tmp/eksctl /usr/local/bin
       eksctl version
       

Step-7: Create EKS Cluster
     
       eksctl create cluster --name cp-cluster --region ap-south-1
       sudo kubectl get node
       sudo kubectl get pods -A -o wide
              




