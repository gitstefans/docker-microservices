FROM alpine/git as sourcecode

RUN git clone https://github.com/kkenan/basic-microservices.git

FROM node:9.9.0-alpine

WORKDIR /app

COPY --from=sourcecode /git/basic-microservices/node-app/package.json /app

RUN npm install

COPY --from=sourcecode /git/basic-microservices/node-app /app

EXPOSE 8081

CMD ["node", "index.js"]