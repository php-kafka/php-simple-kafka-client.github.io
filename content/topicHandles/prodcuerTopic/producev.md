---
title: "producev"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function producev(
    int $partition,
    int $msgFlags,
    ?string $payload = null,
    ?string $key = null,
    ?array $headers = null,
    ?int $timestampMs = null
): void {}
```
Produce a message and additional data to a topic partition  
This is an asynchronous and non-blocking call
## Parameter details
partition: can be either a partition number or `RD_KAFKA_PARTITION_UA` for automatic partitioning  
msgflags: `0` or `RD_KAFKA_MSG_F_BLOCK` to block the producer if the queue is full  
key: message key, if non-null the topic partitioner will calculate the partition according to the key  
## Example
```php
$conf = new SimpleKafkaClient\Configuration();
$conf->set('auto.offset.reset', 'earliest');
$producer = new SimpleKafkaClient\Producer($conf);
$producerTopic = $producer->getTopicHandle('test-topic');
$producerTopic->produce(
    RD_KAFKA_PARTITION_UA,
    RD_KAFKA_MSG_F_BLOCK, // will block produce if queue is full
    'some message',
    'message-key',
    [
        'some header' => 'some header value'
    ],
    round(microtime(true) * 1000) //timestam for this event
);
```
{{< hint danger >}}
If you are done producing messages, you need to call `flush()`  
If you do not call `flush()`, it can lead to message loss
{{< /hint >}}