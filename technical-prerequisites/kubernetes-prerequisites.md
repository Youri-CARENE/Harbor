# Prérequis techniques pour Kubernetes

## Configuration de Kubernetes pour Harbor

Harbor peut être installé sur un cluster Kubernetes pour une meilleure gestion et scalabilité. Voici les étapes à suivre pour préparer Kubernetes à l'installation de Harbor.

### Installation de Kubernetes

Si Kubernetes n'est pas déjà installé, voici comment procéder.

#### Installation via kubeadm sur Ubuntu

```bash
sudo apt update
sudo apt install -y apt-transport-https ca-certificates curl
sudo curl -fsSL https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
sudo apt-add-repository "deb http://apt.kubernetes.io/ kubernetes-xenial main"
sudo apt update
sudo apt install -y kubelet kubeadm kubectl
sudo kubeadm init
