---
title: "getCommittedOffsets"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function getCommittedOffsets(array $topics, int $timeoutMs): array {}
```
Returns the committed offsets for topics and partitions for a consumer group
## Example
```php
$conf = Kafka\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$consumer = new Kafka\Consumer($conf);
$topicPartition = new TopicPartition('test-topic', 0);
var_dump($consumer->getCommittedOffsets([$topicPartition], 10000));
```