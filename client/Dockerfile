# 1. Image de base
FROM node:lts-alpine

# 2. Répertoire de travail
WORKDIR /app

# 3. Définir la variable d'environnement pour l'API React (build time / runtime)
ARG REACT_APP_API_URL=http://localhost:9000
ENV REACT_APP_API_URL=$REACT_APP_API_URL

# 4. Copie et installation des dépendances
COPY package*.json ./
RUN npm install

# 5. Copier le code
COPY . .

# 6. Construire l'application React
RUN npm run build

# 7. Installer le serveur HTTP léger `serve`
RUN npm install -g serve

# 8. Exposer le port du client
EXPOSE 3000

# 9. Lancer `serve` sur le dossier build
CMD ["serve", "-s", "build", "-l", "3000"]