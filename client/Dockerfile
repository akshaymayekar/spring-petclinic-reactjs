FROM node:10.23-alpine

WORKDIR /app
COPY package*.json /app/
RUN npm install
COPY . /app/
EXPOSE 3000:3000

CMD ["npm", "start"]