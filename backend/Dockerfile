FROM node:18-alpine3.15 AS builder
WORKDIR ./
COPY *.json ./
RUN npm install
COPY . .
RUN npm run build

FROM node:18-alpine3.15
WORKDIR ./
COPY --from=builder ./ ./
EXPOSE 8000
CMD ["npm", "run", "start:prod"]