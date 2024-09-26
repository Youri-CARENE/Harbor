
# Installation de Harbor sur un seul nœud

## Prérequis

Avant de commencer l'installation de Harbor, assurez-vous que les éléments suivants sont configurés :

- Docker est installé (voir [prérequis techniques Docker](../02-technical-prerequisites/docker-prerequisites.md)).
- Docker Compose est installé.

## Étapes

### 1. Télécharger le package d'installation de Harbor

```bash
wget https://github.com/goharbor/harbor/releases/download/v2.4.2/harbor-online-installer-v2.4.2.tgz
tar xvf harbor-online-installer-v2.4.2.tgz
cd harbor
```

### 2. Configurer le fichier `harbor.yml`

Modifiez le fichier `harbor.yml` pour personnaliser votre installation. Vous pouvez configurer :

- Le port sur lequel Harbor sera accessible.
- Le nom de domaine ou l'adresse IP du serveur.
- Les certificats SSL pour sécuriser l'accès à Harbor.

Par exemple, dans `harbor.yml` :

```yaml
hostname: <IP ou nom_de_domaine>
http:
  port: 80
# ssl:
#   certificate: /path/to/cert
#   private_key: /path/to/key
```

### 3. Lancer le script d'installation

Une fois les modifications apportées au fichier `harbor.yml`, exécutez le script d'installation :

```bash
sudo ./install.sh
```

### 4. Vérifier l'installation

Lorsque l'installation est terminée, accédez à l'interface utilisateur de Harbor via votre navigateur à l'adresse suivante :

```bash
http://<IP ou nom_de_domaine>:<port>
```

Par défaut, Harbor est accessible sur le port 80 si SSL n'est pas configuré.

---

## Résolution des problèmes

### 1. Port utilisé par une autre application

Si vous rencontrez des problèmes avec des ports déjà utilisés, vous pouvez soit modifier le port dans le fichier `harbor.yml`, soit arrêter l'application qui occupe le port.

### 2. Problèmes de certificat SSL

Si vous avez activé SSL, assurez-vous que les chemins des certificats sont corrects et que le serveur dispose des permissions nécessaires pour y accéder.

