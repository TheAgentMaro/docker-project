# Projet Docker Swarm - Application de Vote

- Ce projet consiste à containeriser une application de vote distribuée en utilisant Docker et à la déployer sur un cluster Docker Swarm.

## Exécution de l'Application Localement

- Pour exécuter l'application localement, suivez les étapes ci-dessous :

### Prérequis

- Assurez-vous d'avoir Docker et Docker Compose installés sur votre système.
- Pour utiliser ubuntu sous windows vous devez installer WSL

   ```bash
   wsl --install

- Documentation microsoft WSL :' https://learn.microsoft.com/fr-fr/windows/wsl/install '

- Installation Dotnet (Ubuntu "WSL) :
    ```bash
    sudo apt-get update
    sudo apt-get install -y dotnet-sdk-7.0.
    sudo apt-get install -y aspnetcore-runtime-7.0.
    sudo apt-get install -y dotnet-runtime-7.0.
    sudo apt install zlib1g.
    dotnet -v (#Verification Version)

- Installation Nodejs (Ubuntu "WSL)
    ```bash
    sudo apt-get update
    sudo apt install nodejs
    node -v (#Verification Version)

- Installation Python (Ubuntu "WSL)
    ```bash
    sudo apt-get update
    sudo apt install python3.11
    python -v (#Verification Version)

- Path access verification Package.json  "server.js" ("PATH TO server.js exp = //wsl.localhost/Ubuntu/home/user/docker-project/result/server.js )


### Étapes


1. Clonez ce référentiel dans un répertoire local :

   ```bash
   git clone https://github.com/TheAgentMaro/docker-project.git```

2. Accédez au répertoire du projet :

   ```bash
   cd docker-project```

#### Methode 1 (Utilisation Docker Compose) :

1. Construction des images Docker :

   ```bash
      docker build -t result-app ./result
      docker build -t vote-app ./vote
      docker build -t worker-app ./worker
   ```

2. Lancement du Docker Compose :

   ```bash
   docker-compose up -d```

- Cela téléchargera les images Docker nécessaires, construira les images pour les modules "result," "vote," et "worker," puis démarrera tous les services en une seule commande :.

3. Une fois les services démarrés, ouvrez un navigateur web et accédez à l'interface de l'application "result" via l'adresse http://localhost:80, et à l'interface de l'application "vote" via l'adresse http://localhost:8080.

#### Méthode 2 (Exécution manuelle avec des scripts) :

1.  Ouvrez un terminal, puis naviguez vers le répertoire racine de votre projet "docker-project" où se trouvent les scripts "run" et le fichier docker-compose.yml.

2.  Avant de commencer, assurez-vous que Docker est installé sur votre système.

3.  Exécutez les scripts dans l'ordre indiqué, de 1 à 5, dans des terminaux séparés. Vous pouvez le faire en utilisant les commandes suivantes :

- Redis :
      ```bash
      bash ./run/step-1.bash```

- l'application "vote" :
      ```bash
      bash ./run/step-2.bash```

- PostgreSQL :
      ```bash
      bash ./run/step-3.bash```

-  l'application "worker" :
      ```bash
      bash ./run/step-4.bash```

- l'application "result" :
      ```bash
      bash ./run/step-5.bash```

4. Une fois les scripts exécutés, les différentes parties de l'application devraient être accessibles localement. Vous pouvez accéder à l'interface "result" en ouvrant un navigateur et en visitant l'adresse http://localhost:80, et à l'interface "vote" à l'adresse http://localhost:8080.

5. Remettre le projet dans son état initial :
      ```bash
    bash ./run/reset.bash

## Déploiement d'un Cluster Docker Swarm

### Prérequis

- Vous devez avoir accès à un cluster Docker Swarm avec au moins un nœud manager et deux nœuds worker.

### Étapes

1. Construisez les images Docker pour les modules "result," "vote," et "worker" sur votre système local. Vous pouvez utiliser la commande docker build pour cela.

      ```bash
    docker build -t

2. Exportez les images vers un registre Docker, tel que Docker Hub, en utilisant docker push.

3. Sur votre cluster Docker Swarm, créez un fichier docker-compose.yml similaire à celui du projet local. Assurez-vous que le fichier contient les bonnes images Docker depuis le registre.

4. Déployez l'application sur le cluster Docker Swarm en utilisant la commande docker stack deploy avec votre fichier docker-compose.yml.

   ```bash
   docker stack deploy -c docker-compose.yml vote-app```

5. L'application sera déployée sur votre cluster Docker Swarm et sera accessible via les adresses des nœuds manager ou via un équilibreur de charge si configuré.

#### C'est tout ! Vous avez maintenant déployé l'application de vote sur un cluster Docker Swarm.

## Contributeurs

- Mohamed Marwen Meddeb - Student Engineer SUPINFO | Full Stack Developer



