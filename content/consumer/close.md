---
title: "close"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function close(): void {}
```
Close down the Consumer. This call will block until  
the consumer has revoked its assignment, calling the rebalance callback  
if it is configured, committed offsets to broker, and left the consumer group. The maximum blocking time is roughly limited to session.timeout.ms.
## Example
```php
$conf = Kafka\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$consumer = new Kafka\Consumer($conf);
$consumer->close();
```