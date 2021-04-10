---
title: "queryWatermarkOffsets"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function queryWatermarkOffsets(string $topic, int $partition, int &$low, int &$high, int $timeoutMs): void {}
```
Query broker for low (oldest) and high (newest) offsets for a partition
## Example
```php
$low = 0;
$high = 0;

$conf = SimpleKafkaClient\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$consumer = new SimpleKafkaClient\Consumer($conf);
$topicPartition = new TopicPartition('test-topic', 0, strtotime("-1 week"));
$consumer->queryWatermarkOffsets('test-topic', 0, int &$low, int &$high, 10000);
```