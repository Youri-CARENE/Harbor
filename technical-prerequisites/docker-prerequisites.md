# Prérequis techniques pour Docker

## Installation de Docker

Avant d'installer Harbor, il est essentiel d'avoir Docker configuré correctement. Voici les étapes pour installer Docker sur différentes plateformes.

### Installation sur Ubuntu

```bash
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
sudo add-apt-repository "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt update
sudo apt install docker-ce
