# Image de base Python compatible avec votre application
FROM python:3.11

# Répertoire de travail
WORKDIR /app

# Le code source de l'application
COPY . /app

# Les dépendances Python
RUN pip install -r requirements.txt

# Le port sur lequel l'application écoute
EXPOSE 8080

# Commande pour démarrer l'application
CMD ["python", "app.py"]