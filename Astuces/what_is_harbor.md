
# C'est quoi Harbor ?

## Introduction à Harbor

Harbor est un **registry de conteneurs open source** qui permet de stocker, signer et scanner les images Docker. Développé à l'origine par VMware, Harbor est maintenant un projet incubé par la Cloud Native Computing Foundation (CNCF). 

Le but de Harbor est de fournir une solution complète pour la gestion des images de conteneurs, avec des fonctionnalités de sécurité avancées, la gestion des accès et des permissions, ainsi que des mécanismes pour assurer la conformité et la sécurité des conteneurs utilisés dans un environnement de production.

### Fonctionnalités principales

- **Stockage d'images** : Harbor stocke des images Docker et d'autres formats d'artefacts OCI.
- **Contrôle d'accès basé sur les rôles (RBAC)** : Les utilisateurs et les projets peuvent être gérés avec des permissions spécifiques.
- **Scannage des vulnérabilités** : Harbor intègre des outils de scannage pour détecter les vulnérabilités dans les images conteneurs.
- **Signature d'images** : Il est possible de signer les images pour garantir leur intégrité.
- **Multi-tenant** : Harbor permet la gestion de multiples projets avec des règles de permissions spécifiques.
- **Support pour plusieurs registres** : Harbor peut se synchroniser avec d'autres registres externes comme DockerHub ou Quay.

### Pourquoi utiliser Harbor ?

1. **Sécurité renforcée** : Avec son système de scannage et de signature, Harbor offre des garanties importantes en matière de sécurité.
2. **Gestion des accès** : Le contrôle d'accès basé sur les rôles permet de limiter et d'organiser les accès aux différentes ressources.
3. **Open Source** : Harbor est entièrement gratuit et supporté par une communauté active de développeurs.
4. **Extensible** : Harbor peut être intégré à d'autres outils DevOps comme Kubernetes, GitLab CI, Jenkins, etc.

---

## Architecture de Harbor

Harbor se compose de plusieurs composants qui fonctionnent ensemble pour fournir un service complet :

1. **Registry** : Le registre principal qui stocke les images Docker.
2. **Core Service** : Le service central qui gère l'authentification, les projets, les permissions et les API.
3. **Job Service** : Gère les tâches asynchrones, comme le scannage des images et les réplications entre registres.
4. **Database** : Stocke toutes les métadonnées concernant les images, les utilisateurs et les permissions.
5. **Clair** : Outil intégré pour scanner les vulnérabilités dans les images.
6. **Notary** : Outil de Docker qui permet de signer les images.

---

