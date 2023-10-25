# Utilisez une image de base Node.js compatible avec votre application
FROM node:18

# Définissez le répertoire de travail
WORKDIR /app

# Copiez le code source de l'application
COPY . /app

# Installez les dépendances Node.js
RUN npm install

# Exposez le port sur lequel l'application écoute
EXPOSE 80

# Commande pour démarrer l'application
CMD ["npm", "start"]