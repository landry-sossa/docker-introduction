# Utiliser l'image officielle node légère, branche alpine 18.x
FROM node:18-alpine

# Définir /app comme répertoire de travail
WORKDIR /app

# Copier les fichiers package.json et package-lock.json
#COPY package*.json ./

# Copier TOUT le code source (index.html, main.js, public, images, etc.)
COPY . .

# Installer, construire et nettoyer en une seule instruction
RUN npm install && \
    npm install -g serve && \
    npm run build && \
    rm -fr node_modules

# Exposer le port 3000 (port par défaut de l'application)
EXPOSE 3000

# Démarrer l'application avec la syntaxe de tableau JSON
CMD ["serve", "-s", "dist"]
