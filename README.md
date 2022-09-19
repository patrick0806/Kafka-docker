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
 
 
