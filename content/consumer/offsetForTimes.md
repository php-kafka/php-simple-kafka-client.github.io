---
title: "offsetsForTimes"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function offsetsForTimes(array $topicPartitions, int $timeoutMs): array {}
```
Look up the offsets for the given partitions by timestamp.  
The returned offset for each partition is the earliest offset whose  
timestamp is greater than or equal to the given timestamp in the  
corresponding partition.
## Example
```php
$conf = SimpleKafkaClient\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$consumer = new SimpleKafkaClient\Consumer($conf);
$topicPartition = new TopicPartition('test-topic', 0, strtotime("-1 week"));
$offsetsOneWeekAgo = $consumer->offsetForTimes([$topicPartition], 10000);
```