---
title: "subscribe"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function subscribe(array $topics): void {}
```
Subscribe to one or more topics (regexp also supported).  
Any previous subscription will be unassigned and unsubscribed first.  

## Example
```php
$conf = Kafka\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$consumer = new Kafka\Consumer($conf);
$consumer->subscribe(['test-topic']);
```