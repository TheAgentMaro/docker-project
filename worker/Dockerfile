# Une image de base compatible avec .NET Core
FROM mcr.microsoft.com/dotnet/aspnet:7.0 AS base
WORKDIR /app

# Les fichiers de publication dans le conteneur
COPY . .

# Commande pour démarrer le worker
CMD ["dotnet", "bin/release/net7.0/Worker.dll"]
