FROM node:10.23-alpine

WORKDIR /app
COPY package*.json /app/
RUN npm install
COPY . /app/
CMD ["npm", "start"]
