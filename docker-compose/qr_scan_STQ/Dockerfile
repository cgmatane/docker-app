# Stage 0, Build de l'app du code qr

FROM node:alpine as build-stage

WORKDIR /app

COPY ./qr-code-scanner/package*.json /app/

RUN npm install

COPY ./qr-code-scanner/ /app/

RUN npm run build

# Stage 1, Déploiement de l'app avec un serveur web nginx

FROM nginx:alpine

COPY --from=build-stage /app/dist/ /var/www/

COPY ./nginx.conf /etc/nginx/conf.d/default.conf

