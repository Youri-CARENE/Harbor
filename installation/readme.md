# Guide d'installation de Harbor

Ce guide fournit des instructions détaillées pour installer Harbor dans différents environnements. Harbor peut être installé sur une seule machine ou distribué sur plusieurs nœuds pour plus de résilience.

## Installation sur un seul nœud

### Prérequis

- Docker installé (voir [docker-prerequisites.md](../02-technical-prerequisites/docker-prerequisites.md))
- Docker Compose installé

### Étapes

1. **Télécharger le package d'installation de Harbor**

```bash
wget https://github.com/goharbor/harbor/releases/download/v2.4.2/harbor-online-installer-v2.4.2.tgz
tar xvf harbor-online-installer-v2.4.2.tgz
cd harbor
