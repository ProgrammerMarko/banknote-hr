# 1. Base Image: Uzimamo laganu verziju Node-a (Alpine Linux)
FROM node:20-alpine

# 2. Radni direktorij unutar kontejnera (standardna Linux praksa)
WORKDIR /usr/src/app

# 3. SENIOR TRIK: Kopiramo SAMO definicije paketa
# Ovo omogućuje Dockeru da kešira "npm install" ako se paketi nisu mijenjali
COPY package*.json ./

# 4. Instalacija paketa
RUN npm install

# 5. Kopiramo ostatak izvornog koda
# Ovo se izvršava tek nakon install-a, pa promjene u kodu ne kvare cache paketa
COPY . .

# 6. Pokrećemo u Development modu (tvoja odluka iz prethodnog koraka)
CMD ["npm", "run", "start:dev"]