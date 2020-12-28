---
title: "commitTransaction"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function commitTransaction(int $timeoutMs): void {}
```
Get a producer instance
## Example
```php
$conf = Kafka\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$producer = new Kafka\Producer($conf);
```