don't mind about node_module, just http-server .
and go to http://localhost:8080/example/balance.html

server side:

use docker:
docker run -v /home/pallat/ethereum:/root \
           -p 8545:8545 -p 30303:30303 \
           ethereum/client-go --testnet -ipcapi admin,eth,miner --rpcapi admin,eth,web3,miner,personal --rpc --rpcaddr "0.0.0.0" --rpccorsdomain "http://localhost:8080"

attach to docker:
docker exec -it {docker ps id} geth attach http://localhost:8545
