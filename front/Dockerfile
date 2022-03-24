FROM node:16.14.0-alpine AS build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

FROM nginx
COPY --from=build /app/dist/tlcfront /usr/share/nginx/html

