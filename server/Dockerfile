# 1. Image de base légère
FROM node:lts-alpine

# 2. Définir le répertoire de travail
WORKDIR /app

# 3. Copier les fichiers de dépendances
COPY package*.json ./

# 4. Installer les dépendances
RUN npm install

# 5. Copier le reste du code source
COPY . .

# 6. Exposer le port du serveur Express
EXPOSE 9000

# 7. Variable d'environnement par défaut
ENV MONGO_URI=mongodb://mongodb:27017/mern

# 8. Commande de démarrage
CMD ["npm", "start"]