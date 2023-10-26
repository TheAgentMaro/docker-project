# Utilisez une image de base Node.js compatible avec votre application
FROM node:18

# Le répertoire de travail
WORKDIR /app

# Copiez le code source de l'application
COPY . /app

# Installez les dépendances Node.js
RUN npm install

# Exposez le port sur lequel l'application écoute (Environnement du port de Node.js)
EXPOSE 8081

# Commande pour démarrer l'application
CMD ["npm", "start"]