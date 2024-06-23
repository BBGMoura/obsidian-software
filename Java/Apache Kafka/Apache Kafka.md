https://kafka.apache.org/intro

An event streaming platform that can scale massive pipelines of real time data.

Event streaming is the practice of capturing data in real-time from event sources like databases, sensors, mobile devices, cloud services, and software applications in the form of streams of events; storing these events streams durably for later retrieval; manipulating, processing, and reacting to the event stream in real-time as well as retrospectively; and routing the vent stream to different destination technologies as needed.

## Example Usages
Event streaming is applied to a wide variety of use cases. It's many examples include:
- To process payments and financial transactions in real-time, such as stock exchanges.
- To track and monitor cars, trucks, fleets, and shipments in real-time, such as in logistics and automotive industry.
- To collect and immediately react to customer interactions and orders, such as in retail, the hotel and travel industry and mobile applications. 
- To monitor patients in hospital care and predict changes in condition to ensure timely treatment in emergencies.

## Kafka Event Streaming. What does this mean?
Kafka combines three key capabilities so you can implement your use cases for event streaming end-top-end with a single battle-tested solution:
- To publish (write) and subscribe to (read) stream of events, including continuous import/export of your data from other systems.
- To store streams of events durably and reliably as long as required
- To process streams of events as they occur or retrospectively.
## How does it work?
 1. When an event occurs, for example a site visit, the producer API produces a Record. 
 2. The records are stored to disk in an ordered, immutable log. This is called a Topic.
 3. Topics can persist forever, or disappear when needed.
 4. Topics are  distributed and replicated in a cluster, which contains multiple servers called Brokers. This is makes it fault-tolerant and able to scale to any work load as there are several servers which can take over if one fails.
 5. Kafka is run as a cluster of one or more servers which include these Broker servers and servers which run Kafka Connect.
 6. Kafka Connect servers continuously import and export data as event streams to integrate Kafka with your existing database.
 7. Multiple consumers can subscribe to the data.
 8. Consumers are able to  read only one record, several records or subscribe to event data in real-time.
 9. Kafka also produces are powerful stream API which can transform the data before it reaches the consumer.

## Main Concepts and Terminology 
**Events**
An event records something happening. It is also called record or message in the documentation. When you read or write data to Kafka, this is done in form of events.

An event has:
- key
- value
- timestamp
- optional metadata headers

Example event:
- key: "Alice"
- value: "made payment of £200 to bob"
- timestamp:  "Jun. 25, 2020 at 2:06 p.m."

**Producers and Consumers**
Producers are client applications that publish (write) events to Kafka. Consumers are those which subscribe to (read and process) the events. They are ful

**Topics**
Events are organised and durably stored in topics. A topic is similar to a folder in a filesytem. The events are like the files in the folder. An example topic name would be "payments".  Topics in Kafka are multi-producer and multi-subscriber. A topic can have zero, one, or many producers that write events to it, as well as zero, one, or many consumers that subscribe to these events. Events in a topic can be read as often as needed— events are not deleted after consumption. Instead, you define for how long Kafka should retain your events through a per-topic configuration setting, after which old events will be discarded. Kafka's performance is effectively constant with respect to data size, so storing data for a long time is perfectly fine.

Topics are partitioned, meaning a topic is spread over a number of "buckets" located on different Kafka brokers. This distribution of data is important as it allows client applications to both read and write to many brokers at the same time.


When a new event is published to a topic, it is actually appended to one of the topic's partitions. Events with the same event key (e.g., a customer or vehicle ID) are written to the same partition, and Kafka guarantees that any consumer of a given topic-partition will always read that partition's events in exactly the same order as they were written.

![[Kafka parttiion.png]]

## Kafka APIs
- The [Admin API](https://kafka.apache.org/documentation.html#adminapi) to manage and inspect topics, brokers, and other Kafka objects.
- The [Producer API](https://kafka.apache.org/documentation.html#producerapi) to publish (write) a stream of events to one or more Kafka topics.
- The [Consumer API](https://kafka.apache.org/documentation.html#consumerapi) to subscribe to (read) one or more topics and to process the stream of events produced to them.
- The [Kafka Streams API](https://kafka.apache.org/documentation/streams) to implement stream processing applications and microservices. It provides higher-level functions to process event streams, including transformations, stateful operations like aggregations and joins, windowing, processing based on event-time, and more. Input is read from one or more topics in order to generate output to one or more topics, effectively transforming the input streams to output streams.
- The [Kafka Connect API](https://kafka.apache.org/documentation.html#connect) to build and run reusable data import/export connectors that consume (read) or produce (write) streams of events from and to external systems and applications so they can integrate with Kafka. For example, a connector to a relational database like PostgreSQL might capture every change to a set of tables. However, in practice, you typically don't need to implement your own connectors because the Kafka community already provides hundreds of ready-to-use connectors.