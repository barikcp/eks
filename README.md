# EKS Cluster
Step-1: Create an EC2 instance as controller machine.

Step-2: Connect the EC2 instance from command prompt.

Step-3: Install "awscli"
> apt update
> apt install awscli

Step-4: Create access key
Services -> IAM -> Dashboard -> Manage Access key -> Create New access Key

Step-5: Configure AWS
> aws configure


Step-6: Install Kubectl
> curl -O https://s3.us-west-2.amazonaws.com/amazon-eks/1.23.13/2022-10-31/bin/linux/amd64/kubectl
> openssl sha1 -sha256 kubectl
> chmod +x ./kubectl
> mkdir -p $HOME/bin && cp ./kubectl $HOME/bin/kubectl && export PATH=$PATH:$HOME/bin
> kubectl version --short --client


        wget https://github.com/k3s-io/k3s/releases/download/v1.23.5%2Bk3s1/k3s   # Download the binary

        chmod +x k3s ​                                                            # Give Executable permission  

        sudo ./k3s server​                                                        # Install K3s cluster in Master Node   
        
        sudo ./k3s kubectl get nodes -o wide                                      # Check how many nodes got created
        curl -O https://s3.us-west-2.amazonaws.com/amazon-eks/1.23.13/2022-10-31/bin/linux/amd64/kubectl
        openssl sha1 -sha256 kubectl
        chmod +x ./kubectl
        mkdir -p $HOME/bin && cp ./kubectl $HOME/bin/kubectl && export PATH=$PATH:$HOME/bin
        kubectl version --short --client
         



Step-7: Install eksctl
> curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
> sudo mv /tmp/eksctl /usr/local/bin
> eksctl version

Step-8: Create EKS Cluster
> eksctl create cluster --name cp-cluster --region ap-south-1
> sudo kubectl get node
> sudo kubectl get pods -A -o wide

 




