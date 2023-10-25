# Projet Docker Swarm - Application de Vote

- Ce projet consiste à containeriser une application de vote distribuée en utilisant Docker et à la déployer sur un cluster Docker Swarm.

## Exécution de l'Application Localement

- Pour exécuter l'application localement, suivez les étapes ci-dessous :

### Prérequis

- Assurez-vous d'avoir Docker et Docker Compose installés sur votre système.

### Étapes

1. Clonez ce référentiel dans un répertoire local :

   ```bash
   git clone https://github.com/TheAgentMaro/docker-project.git```

2. Accédez au répertoire du projet :

   ```bash
   cd docker-project```

3. Construisez et démarrez les conteneurs Docker avec Docker Compose :

   ```bash
   docker-compose up -d```

- Cela téléchargera les images Docker nécessaires, construira les images pour les modules "result," "vote," et "worker," puis démarrera tous les services.

4. Une fois les services démarrés, ouvrez un navigateur web et accédez à l'interface de l'application "result" via l'adresse http://localhost:80, et à l'interface de l'application "vote" via l'adresse http://localhost:8080.

5. Vous pouvez maintenant interagir avec l'application et effectuer des votes.

## Déploiement d'un Cluster Docker Swarm

### Prérequis

- Vous devez avoir accès à un cluster Docker Swarm avec au moins un nœud manager et deux nœuds worker.

### Étapes

1. Construisez les images Docker pour les modules "result," "vote," et "worker" sur votre système local. Vous pouvez utiliser la commande docker build pour cela.

2. Exportez les images vers un registre Docker, tel que Docker Hub, en utilisant docker push.

3. Sur votre cluster Docker Swarm, créez un fichier docker-compose.yml similaire à celui du projet local. Assurez-vous que le fichier contient les bonnes images Docker depuis le registre.

4. Déployez l'application sur le cluster Docker Swarm en utilisant la commande docker stack deploy avec votre fichier docker-compose.yml.

   ```bash
   docker stack deploy -c docker-compose.yml vote-app```

5. L'application sera déployée sur votre cluster Docker Swarm et sera accessible via les adresses des nœuds manager ou via un équilibreur de charge si configuré.

#### C'est tout ! Vous avez maintenant déployé l'application de vote sur un cluster Docker Swarm.

## Contributeurs

- Mohamed Marwen Meddeb - Student Engineer | Full Stack Developer



