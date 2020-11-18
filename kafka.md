It is an event streaming platform used to collect, process, store, and integrate data at scale. 
It models events as key/value pairs. It is a distributed commit log which are splitted into partitions.

Each message in a topic is assigned a sequential ID called offset. Writes to a partition are generaly sequential
Reading can be from beginnning or direct if offset is provided.

Message are written to partition based on a hash key, which tells which partition to write to.

Use cases - 
    Data integration
    Metrics and Monitoring
    Stream processing
    Distributed log aggregation
    Pub/Sub messaging

Features - 
    High Throughput
    Highly distributed systems with no downtime
    no data loss
    Durability - immutable logs
    Replication of log across different brokers.


Terms - 
    Publisher  - Radio Channel

    Subscriber - Radio listeners
    
    Topic - Frequency
    A feed name to which records are published. It is a log of events. Every topic can be configured to expire data after it has reached a certain age. Logs are immutable.

    Partitions - Topics are broken into ordered commit logs called partition.

    Broker - Kafka cluster is a set of servers or nodes called broker (Towers)

    Zookeper - used for managing and coordianting kafka brokers.

Pros - 
 In Kafka, consumer groups provide ordered delivery across an arbitrary number of consumers, so you get horizontal scale in the consuming application with the strongest ordering guarantee possible, while operating at scale.

    
    
