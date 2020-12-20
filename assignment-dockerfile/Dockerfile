FROM node:14.15.3-alpine

EXPOSE 3000

RUN apk add --no-cache tini

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm install && npm cache clean --force

COPY . .

ENTRYPOINT ["/sbin/tini", "--"]

CMD ["node", "app.js"]
