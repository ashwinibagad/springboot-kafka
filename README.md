# springboot-kafka

1. Producer
Sends data (messages) to Kafka
Publishes messages to a topic
Can choose partition (by key or round-robin)
Doesn't know which consumer will read the data

2. Topic - something like a tunnel where logically grouped messages are stored
Logical category or stream of data
Messages are stored inside partitions

3. Partition

Physical storage unit of a topic
Provides parallelism
Messages inside a partition are ordered

4. Consumer
Reads messages from topics
Pull-based (consumer asks kafka for data)
Belongs to a consumer group

5. Consumer Group
Group of consumers working together
Each partition -> only one consumer in the group 
Enables -> Scalability, Load balancing, Fault tolerance

6. Broker
Kafka server that stores data
Handles producer and consumer requests
cluster = multiple brokers


Zookeeper -> maintains metadata for kafka producer, consumer, broker
from 2.8 (KRaft) onwards, zookeeper is deprecated


start zookeeper
**zookeeper-server-start.bat zookeeper.properties

start kafka server
**kafka-server-start.bat server.properties

to create another server, clone server2.properties and add partition details if needed

create topic
**kafka-topics.bat --create --topic firstTopic --bootstrap-server localhost:9092 --partitions 4 --replication-factor 2

to get topic details
**kafka-topics.bat --describe --topic firstTopic --bootstrap-server localhost:9092

get list of topics created
**kafka-topics.bat --list --bootstrap-server localhost:9092

