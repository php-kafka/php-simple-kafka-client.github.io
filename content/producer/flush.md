---
title: "flush"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function flush(int $timeoutMs): int {}
```
Get a producer instance
## Example
```php
$conf = Kafka\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$producer = new Kafka\Producer($conf);
// produce some messsages
$producer->flush(10000);
```