#There's an official Ethereum docker file so I'll use that as a base.
FROM ethereum/client-go

# I need a few tool to run the agent for eth-netstat on the nodes, I fetch them here.
RUN apk add --update git bash nodejs nodejs-npm perl


# Here I fetch the api from Cuebdro's repository.
RUN cd /root &&\
    git clone https://github.com/cubedro/eth-net-intelligence-api &&\
    cd eth-net-intelligence-api &&\
    npm install &&\
    npm install -g pm2

ADD start.sh /root/start.sh
ADD app.json /root/eth-net-intelligence-api/app.json
RUN chmod +x /root/start.sh

ENTRYPOINT /root/start.sh

