FROM node:8-alpine

RUN apk add --update git

RUN git clone https://github.com/cubedro/eth-netstats

WORKDIR /ethereum-netstat

RUN npm install
RUN npm install -g grunt-cli
RUN grunt

EXPOSE 3000

CMD ["npm", "start"]
