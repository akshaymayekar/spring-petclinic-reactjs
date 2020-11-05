
FROM node:13.12.0-alpine as build
WORKDIR /app
ENV PATH /app/node_modules/.bin:$PATH
COPY package.json ./
COPY package-lock.json ./
RUN npm install
COPY . ./
ARG API_SERVER_URL_ARG
ENV API_SERVER_URL=$API_SERVER_URL_ARG
RUN npm run build:prod

# production environment
FROM nginx:stable-alpine

COPY nginx.conf /etc/nginx/nginx.conf

## Remove default nginx index page
RUN rm -rf /usr/share/nginx/html/*
COPY --from=build /app/public /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
