---
title: "produce"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function produce(
    int $partition,
    int $msgFlags,
    ?string $payload = null,
    ?string $key = null
): void {}
```
Produce a message to a topic partition  
This is an asynchronous and non-blocking call
## Parameter details
partition: can be either a partition number or `RD_KAFKA_PARTITION_UA` for automatic partitioning  
msgflags: `0` or `RD_KAFKA_MSG_F_BLOCK` to block the producer if the queue is full  
key: message key, if non-null the topic partitioner will calculate the partition according to the key
## Example
```php
$conf = new Kafka\Configuration();
$conf->set('auto.offset.reset', 'earliest');
$producer = new Kafka\Producer($conf);
$producerTopic = $producer->getTopicHandle('test-topic');
$producerTopic->produce(
    RD_KAFKA_PARTITION_UA,
    RD_KAFKA_MSG_F_BLOCK, // will block produce if queue is full
    'some message',
    'message-key'
);
```
{{< hint danger >}}
If you are done producing messages, you need to call `flush()`  
If you do not call `flush()`, it can lead to message loss
{{< /hint >}}