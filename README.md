# Kafka-docker
## How Running Kafka by docker
Obs: The image docker using here is from https://github.com/confluentinc/cp-docker-images

## Steps

### 1 - Create container
```bash
docker compose up -d
```
 -d is to runnning in second plan
 
 ### 2 - Access de container bash
 ```bash
 docker exec -it kafka_kafka_1 bash
 ```
 
 ### 3 - Create Topic
 ```bash
 kafka-topics --create --bootstrap-server localhost:29092 --replication-factor 1 --partitions 1 --topic topicname
 ```
 
 ### 4 - Create log on topic using producer
 ```bash
 kafka-console-producer --broker-list localhost:29092 --topic topicname
 ```
 
 ### 5 - Listen topic
 ```bash
 kafka-console-consumer --bootstrap-server localhost:29092 --topic topicname
 ```
 
  ### 6 - See past logs
   ```bash
 kafka-console-consumer --bootstrap-server localhost:29092 --topic topicname --from-begining
 ```
 # How running Kafka without Docker
 
 ###  1 - Download Kafka
 go to https://kafka.apache.org/downloads and donwload the binary of last version
 
 ### 2 - create the directory to save kafka
 ```bash
  cp -r  ./kafka_2.13-3.2.3 /usr/local/kafka
 ```
 
 ### 3 - unzip 
 ```bash
 sudo tar xzf kafka-3.2.0-src.tgz --strip 1
 ```
 ### 4 - delete zip file
 ```bash
 sudo rm kafka-3.2.0-src.tgz 
 ```
 
 ### 5 - running zookeeper
 ```bash
 sudo bin/zookeeper-server-start.sh config/zookeeper.properties
 ```
 
 ### 6 - running kafka
 ```bash
 sudo bin/kafka-server-start.sh config/server.properties
 ```
 
 And you can download offset explorer to interact with kafka
 https://www.kafkatool.com/
 
 
 
