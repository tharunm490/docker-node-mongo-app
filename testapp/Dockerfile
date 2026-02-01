FROM node

WORKDIR /testapp

ENV MONGO_DB_USERNAME=admin \
  MONGO_DB_PWD=admin

COPY . .

RUN npm install

EXPOSE 5050

CMD ["node", "server.js"]
