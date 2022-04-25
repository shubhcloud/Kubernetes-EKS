# EKS Setup

# Before Starting you must have the below Pre-Requisites

- Linux Admiistration knowledge is must
- Ansible Automation/Administration Knowledge is must
- AWS account should be created and activated.


| Purpose   | VM Name          | CPU | Memory | Disk  | Operating System |
| -------   | ---------------- | --- | ------ | ----  | ---------------- |
| Machine 1 | EKS              |  1  | 2 GB   | 10 GB | Amazon Linux     |

# EKSCTL installation

**For Linux Machines**

Refer below link to install latest version :
https://github.com/weaveworks/eksctl/releases

**Execute Below command**
```
curl --silent --location "https://github.com/weaveworks/eksctl/releases/download/v0.93.0/eksctl_Linux_amd64.tar.gz" | tar xz -C /tmp 
```
**Move eksctl to bin**
```
sudo mv /tmp/eksctl /usr/bin
```
**Test version**
```
eksctl version
```

# Install Kubectl

**Add the Repo**
```
cat <<EOF > /etc/yum.repos.d/kubernetes.repo
[kubernetes]
name=Kubernetes
baseurl=https://packages.cloud.google.com/yum/repos/kubernetes-el7-x86_64
enabled=1
#gpgcheck=1
#repo_gpgcheck=1
gpgkey=https://packages.cloud.google.com/yum/doc/yum-key.gpg https://packages.cloud.google.com/yum/doc/rpm-package-key.gpg
EOF
```
**Install Kubectl**
```
yum install -y kubectl
```
**Verify Kubectl version**
```
kubectl version --short --client
```
**Check create cluster --help to ensure everything working fine**
```
eksctl create cluster --help
```
**Create EKS cluster**

create the cluster by using YAML file you can download using wget command or directly execute using github link make sure to have same key pair in the YAML or else create you own and edit in YAML file.

```
eksctl create cluster -f eks-course.yaml
```
**Check all the nodes**
```
kubectl get nodes
```
