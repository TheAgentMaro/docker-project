FROM node:18

# Le répertoire de travail
WORKDIR /app

# Le code source de l'application
COPY . /app
    
# Les dépendances Node.js
RUN npm install

# Le port sur lequel l'application écoute
EXPOSE 8081

# Commande pour démarrer l'application (Server.js  Port:8081)
CMD ["node", "server.js"]