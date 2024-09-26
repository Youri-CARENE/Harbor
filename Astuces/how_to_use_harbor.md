
# Comment utiliser Harbor ?

## Installation de Harbor

Pour commencer à utiliser Harbor, il faut d'abord installer Harbor sur votre infrastructure. Voir [Installation Single Node](single_node_installation.md) ou [Installation Multi Node](multi_node_installation.md).

## Interface Utilisateur

Une fois installé, vous pouvez accéder à l'interface utilisateur de Harbor via votre navigateur. L'interface est simple et permet de :

- **Créer des projets** : Les projets sont des espaces dans lesquels vous pouvez stocker des images Docker.
- **Gérer les utilisateurs** : Vous pouvez ajouter ou supprimer des utilisateurs, ainsi que gérer leurs rôles et permissions.
- **Scanner les images** : Vous pouvez scanner vos images pour détecter les vulnérabilités.
- **Configurer des webhooks** : Vous pouvez configurer des notifications pour certaines actions (comme la poussée d'une nouvelle image).
- **Synchronisation avec d'autres registres** : Harbor permet de synchroniser des images avec d'autres registres comme DockerHub ou Quay.

---

## Premiers Pas

### 1. Créer un projet

1. Connectez-vous à l'interface utilisateur de Harbor.
2. Dans le menu de gauche, cliquez sur **Projets** puis sur **Nouveau Projet**.
3. Donnez un nom à votre projet, configurez si vous souhaitez qu'il soit public ou privé, puis cliquez sur **Créer**.

### 2. Pousser une image Docker

1. Une fois le projet créé, vous pouvez pousser des images Docker vers Harbor.
2. Dans votre terminal Docker, connectez-vous au registre Harbor :

```bash
docker login <adresse_de_harbor>
```

3. Construisez votre image Docker et poussez-la vers Harbor :

```bash
docker build -t <adresse_de_harbor>/<nom_du_projet>/<nom_de_l_image>:<tag> .
docker push <adresse_de_harbor>/<nom_du_projet>/<nom_de_l_image>:<tag>
```

### 3. Scanner une image

1. Dans l'interface utilisateur de Harbor, allez dans le projet où se trouve l'image.
2. Sélectionnez l'image, puis cliquez sur **Scanner** pour lancer une analyse de vulnérabilités.

### 4. Signer une image

1. Pour signer une image, assurez-vous que Notary est activé dans les paramètres de Harbor.
2. Poussez l'image signée en utilisant le client Docker :

```bash
docker trust sign <adresse_de_harbor>/<nom_du_projet>/<nom_de_l_image>:<tag>
```

### 5. Configurer des webhooks

1. Allez dans les paramètres de votre projet, puis cliquez sur **Webhooks**.
2. Ajoutez l'URL de votre service webhook pour recevoir des notifications sur les événements importants (nouvelle image, scan terminé, etc.).


