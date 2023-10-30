# k8-s-cluster-creation-in-ubuntu-environment
Learn about how to install k8's with specific version on ubuntu environment
# Setting Up Kubernetes on Ubuntu with Specific Version

This repository contains instructions and commands to set up Kubernetes on Ubuntu with a specific version (1.22.2-00). The following steps will guide you through the process:

### Prerequisites
- An Ubuntu system
- Root or sudo privileges

### Steps

1. Disable Swap:
   Run the following command to disable swap on your system:
sudo swapoff -a

2. Install Dependencies:
Install required dependencies using the following commands:
sudo apt update
sudo apt install -y apt-transport-https ca-certificates curl software-properties-common

3. Add Kubernetes Repository Key:
Add the Kubernetes repository key with the following command:

curl -fsSL https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -


4. Add Kubernetes Repository:
Add the Kubernetes repository to your sources list:

sudo add-apt-repository "deb https://apt.kubernetes.io/ kubernetes-xenial main"



5. Check Available Versions:
You can check the available versions of kubelet, kubectl, and kubeadm by running:
apt-cache madison kubelet kubectl kubeadm

6. Install Specific Versions:
Install the specific versions of kubelet, kubeadm, and kubectl (1.22.2-00) with the following command:

sudo apt install -y kubelet=1.22.2-00 kubeadm=1.22.2-00 kubectl=1.22.2-00

7. Initialize Kubernetes Cluster:
Initialize your Kubernetes cluster, ignoring preflight errors:

sudo kubeadm init --ignore-preflight-errors=all
