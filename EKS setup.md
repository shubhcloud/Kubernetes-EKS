# EKS Setup

#Before Starting you must have the below Pre-Requisites
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

