---
title: "assign"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function assign(array $topics): void {}
```
Atomic assignment of partitions to consume.  
The new `partitions` will replace the existing assignment.
## Example
```php
$conf = Kafka\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$consumer = new Kafka\Consumer($conf);
$consumer->assign(
    [
        new Kafka\TopicPartition('test-topic', 1, 3000),
        new Kafka\TopicPartition('test-topic', 2, 3009)
    ]
);
```