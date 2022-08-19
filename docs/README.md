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
cd blockchain-trace-fabric/blockchain-trace-bcnetwork/webapp
./start.sh

docker exec -e "CORE_PEER_LOCALMSPID=Org1MSP" -e "CORE_PEER_MSPCONFIGPATH=/opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/peerOrganizations/org1.trace.com/users/Admin@org1.trace.com/msp" -e "CORE_PEER_ADDRESS=peer0.org1.trace.com:7051" cli peer chaincode install -n drivercc -v 1.0 -l golang -p github.com/chaincode/drivercc/go/
Error: No such container: cli

docker exec -it cli bash 
```