## etherium-parity-ethstats#

This builds a containerised, self contained, Etherium network.

This netowrk consists of:
> three Etherium nodes.
> Parity built from the latest release
> eth-netstat for the monitoring


# notes
[Parity](https://github.com/paritytech/parity) has docker build files in the docker folder that can be used.



Etherium has an officual docker image on Dockerhub called [ethereum/client-go](https://github.com/ethereum/go-ethereum/)
```
FROM ethereum/client-go
```

[Etherium-netstat](https://github.com/cubedro/eth-netstats) is written by Cubedro, who doesn't have an officual Docker image.
```
apt-get update
apt-get install npm git
npm install
npm install -g grunt-cli
git clone https://github.com/cubedro/eth-netstats
WORKDIR /eth-netstats
grunt
```
expose port 3000
