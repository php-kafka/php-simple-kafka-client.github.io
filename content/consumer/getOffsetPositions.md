---
title: "getOffsetPositions"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function getOffsetPositions(array $topics): array {}
```
The offset field of each requested partition will be set to the offset of the last consumed message + 1  
If there was no previous message `RD_KAFKA_OFFSET_INVALID` will be returned
## Example
```php
$conf = Kafka\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$consumer = new Kafka\Consumer($conf);
$topicPartition = new TopicPartition('test-topic', 0);
$topicPartitionsWithOffsets = $consumer->getOffsetPositions([$topicPartition]));
```