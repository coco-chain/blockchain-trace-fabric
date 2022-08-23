```shell
docker pull hyperledger/fabric-peer:1.2.0 && 
docker pull hyperledger/fabric-orderer:1.2.0 && 
docker pull hyperledger/fabric-ca:1.2.0 && 
docker pull hyperledger/fabric-tools:1.2.0 && 
docker pull hyperledger/fabric-ccenv:1.2.0 && 
docker pull hyperledger/fabric-baseimage:0.4.10 && 
docker pull hyperledger/fabric-baseos:0.4.10 && 
docker pull hyperledger/fabric-couchdb:0.4.10

docker tag hyperledger/fabric-peer:1.2.0 hyperledger/fabric-peer && 
docker tag hyperledger/fabric-orderer:1.2.0 hyperledger/fabric-orderer && 
docker tag hyperledger/fabric-ca:1.2.0 hyperledger/fabric-ca && 
docker tag hyperledger/fabric-tools:1.2.0 hyperledger/fabric-tools && 
docker tag hyperledger/fabric-ccenv:1.2.0 hyperledger/fabric-ccenv && 
docker tag hyperledger/fabric-baseimage:0.4.10  hyperledger/fabric-baseimage && 
docker tag hyperledger/fabric-baseos:0.4.10 hyperledger/fabric-baseos && 
docker tag hyperledger/fabric-couchdb:0.4.10 hyperledger/fabric-couchdb

docker pull hyperledger/fabric-peer && 
docker pull hyperledger/fabric-orderer && 
docker pull hyperledger/fabric-ca && 
docker pull hyperledger/fabric-tools && 
docker pull hyperledger/fabric-ccenv && 
docker pull hyperledger/fabric-baseimage && 
docker pull hyperledger/fabric-baseos && 
docker pull hyperledger/fabric-couchdb

sudo su
cd blockchain-trace-fabric/blockchain-trace-bcnetwork/basic-network
./start.sh

cd ../webapp/
./start.sh

cnpm install
sudo cnpm install -g pm2
rm -rf hfc-key-store
node enrollAdmin.js
node registerUser.js

node app.js

pm2 start app.js
pm2 stop app.js

docker-compose ps
        Name                      Command               State                                           Ports
------------------------------------------------------------------------------------------------------------------------------------------------------
ca.trace.com           sh -c fabric-ca-server sta ...   Up      0.0.0.0:7054->7054/tcp,:::7054->7054/tcp
cli                    /bin/bash                        Up
couchdb                tini -- /docker-entrypoint ...   Up      4369/tcp, 0.0.0.0:5984->5984/tcp,:::5984->5984/tcp, 9100/tcp
orderer.trace.com      orderer                          Up      0.0.0.0:7050->7050/tcp,:::7050->7050/tcp
peer0.org1.trace.com   peer node start                  Up      0.0.0.0:7051->7051/tcp,:::7051->7051/tcp, 0.0.0.0:7053->7053/tcp,:::7053->7053/tcp
peer0.org2.trace.com   peer node start                  Up      0.0.0.0:8051->7051/tcp,:::8051->7051/tcp, 0.0.0.0:8053->7053/tcp,:::8053->7053/tcp
peer0.org3.trace.com   peer node start                  Up      0.0.0.0:9051->7051/tcp,:::9051->7051/tcp, 0.0.0.0:9053->7053/tcp,:::9053->7053/tcp
peer0.org4.trace.com   peer node start                  Up      0.0.0.0:10051->7051/tcp,:::10051->7051/tcp, 0.0.0.0:10053->7053/tcp,:::10053->7053/tcp
peer0.org5.trace.com   peer node start                  Up      0.0.0.0:11051->7051/tcp,:::11051->7051/tcp, 0.0.0.0:11053->7053/tcp,:::11053->7053/tcp

docker exec -e "CORE_PEER_LOCALMSPID=Org1MSP" -e "CORE_PEER_MSPCONFIGPATH=/opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/peerOrganizations/org1.trace.com/users/Admin@org1.trace.com/msp" -e "CORE_PEER_ADDRESS=peer0.org1.trace.com:7051" cli peer chaincode install -n drivercc -v 1.0 -l golang -p github.com/chaincode/drivercc/go/
Error: No such container: cli

docker exec -it cli bash

sudo docker exec -it storage /bin/bash
```

```shell
hyperledger/fabric-peer docker run
https://fabric-chs.readthedocs.io/zh_CN/chs/
https://www.jianshu.com/p/37dcfe9f3dcd
https://blog.csdn.net/qq_39200980/article/details/105407908
https://hyperledger-fabric-zh-cn.readthedocs.io/zh/latest/docs/Peers.html
```