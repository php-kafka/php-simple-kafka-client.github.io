---
title: "getAssignment"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function getAssignment(): array {}
```
Returns the current partition assignment
## Example
```php
$conf = SimpleKafkaClient\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$consumer = new SimpleKafkaClient\Consumer($conf);
$consumer->assign(
    [
        new SimpleKafkaClient\TopicPartition('test-topic', 1, 3000),
        new SimpleKafkaClient\TopicPartition('test-topic', 2, 3009)
    ]
);
var_dump($consumer->getAssignment());
```