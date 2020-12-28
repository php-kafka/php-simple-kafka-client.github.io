---
title: "unsubscribe"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function unsubscribe(): void {}
```
Unsubscribe from the current subscriptions

## Example
```php
$conf = Kafka\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$consumer = new Kafka\Consumer($conf);
$consumer->subscribe(['test-topic']);
$consumer->unsubscribe();
```