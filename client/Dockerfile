FROM node:10.23-alpine

WORKDIR /app
COPY package*.json /app/
RUN npm install
COPY . /app/

CMD ["npm", "start"]

## build environment
#FROM node:13.12.0-alpine as build
#WORKDIR /app
#ENV PATH /app/node_modules/.bin:$PATH
#COPY package.json ./
#COPY package-lock.json ./
#RUN npm install
#COPY . ./
#RUN npm run build:prod
#
## production environment
#FROM nginx:stable-alpine
#COPY --from=build /app/public /usr/share/nginx/html
#EXPOSE 80
#CMD ["nginx", "-g", "daemon off;"]
