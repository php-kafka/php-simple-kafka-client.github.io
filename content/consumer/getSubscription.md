---
title: "getSubscription"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function getSubscription(): array {}
```
Return topic names to which the consumer is currently subscribed to
## Example
```php
$conf = SimpleKafkaClient\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$consumer = new SimpleKafkaClient\Consumer($conf);
$consumer->subscribe(['test-topic']);
var_dump($consumer->getSubscription());
```