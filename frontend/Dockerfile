#STAGE 1
FROM node:18-alpine3.15 AS builder
WORKDIR ./
COPY *.json ./
RUN npm install
COPY . .
RUN npm run export

#STAGE 2
FROM nginx:1.23.1-alpine
COPY nginx.conf /etc/nginx/nginx.conf
COPY --from=builder /out /usr/share/nginx/html