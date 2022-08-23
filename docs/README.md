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

cd docker-fastdfs
sudo docker-compose up -d
sudo docker-compose ps
sudo docker-compose down
sudo docker exec -it fastdfs-storage /bin/bash
cd /fdfs_conf
fdfs_upload_file storage.conf anti-steal.jpg

cd ../blockchain-trace-basic-data
mvn clean package
mvn clean package -Dmaven.test.skip=true

cd ../docker
cd blockchain-fe
ln -s ../blockchain/Dockerfile Dockerfile
cd ..
cp ../blockchain-trace-basic-data/ruoyi-admin/target/ruoyi-admin.jar blockchain-fe/ 

sudo docker-compose build

sudo docker-compose up
sudo docker-compose up -d
sudo docker-compose ps

sudo docker-compose up blockchain-mysql80
sudo docker-compose up -d blockchain-mysql80

mysql -h127.0.0.1 -uroot -p -P3310
blockchain123456

show databases;
use blockchain;

create database blockchain default character set utf8mb4 collate utf8mb4_unicode_ci;
use blockchain;
create user 'blockchain'@'127.0.0.1' identified by 'blockchain123456';
grant all privileges on blockchain.* to 'blockchain'@'127.0.0.1';
flush privileges;

mysql -h127.0.0.1 -uroot -p -P3310 blockchain < ../blockchain-community.sql

sudo docker-compose up blockchain-redis
sudo docker-compose up -d blockchain-redis

sudo docker-compose build

sudo docker-compose up blockchain
sudo docker-compose up -d blockchain

sudo docker-compose logs -f
sudo docker exec -it blockchain-fe bash
sudo docker-compose logs -f blockchain

```

```shell
hyperledger/fabric-peer docker run
https://fabric-chs.readthedocs.io/zh_CN/chs/
https://www.jianshu.com/p/37dcfe9f3dcd
https://blog.csdn.net/qq_39200980/article/details/105407908
https://hyperledger-fabric-zh-cn.readthedocs.io/zh/latest/docs/Peers.html
```

```xml
<!--mybatis自动生成文件-->
            <plugin>
                <groupId>org.mybatis.generator</groupId>
                <artifactId>mybatis-generator-maven-plugin</artifactId>
                <version>1.3.5</version>
                <dependencies>
                    <dependency>
                        <groupId>org.mybatis.generator</groupId>
                        <artifactId>mybatis-generator-core</artifactId>
                        <version>1.3.5</version>
                    </dependency>
                    <dependency>
                        <groupId>mysql</groupId>
                        <artifactId>mysql-connector-java</artifactId>
                        <version>5.1.41</version>
                    </dependency>
                </dependencies>
                <executions>
                    <execution>
                        <id>mybatis generator</id>
                        <phase>package</phase>
                        <goals>
                            <goal>generate</goal>
                        </goals>
                    </execution>
                </executions>
                <configuration>
                    <!--    允许移动文件        -->
                    <verbose>true</verbose>
                    <!-- 允许覆盖文件，应该设置为false ，如果为true 前面生成的映射文件将会被覆盖         -->
                    <overwrite>false</overwrite>
                    <configurationFile>
                        src/main/resources/mybatis-generator.xml
                    </configurationFile>
                </configuration>
            </plugin>
```