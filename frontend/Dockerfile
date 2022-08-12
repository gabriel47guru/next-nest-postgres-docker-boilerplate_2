#STAGE 1
FROM node:18-alpine3.15 AS build
WORKDIR ./
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

#STAGE 2
FROM nginx:1.23.1-alpine
COPY nginx.conf /etc/nginx/nginx.conf
COPY --from=build /out /usr/share/nginx/html