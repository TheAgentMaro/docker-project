# Image de base Python compatible avec votre application
FROM python:3.11

#Rep
WORKDIR /app

# Le code source de l'application
COPY . .

# Les dépendances Python
RUN pip install -r requirements.txt

# Le port sur lequel l'application écoute
EXPOSE 8080

# Commande pour démarrer l'application
CMD ["python", "app.py"]