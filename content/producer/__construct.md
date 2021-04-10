---
title: "__construct"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function __construct(Configuration $configuration) {}
```
Get a producer instance
## Example
```php
$conf = SimpleKafkaClient\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$producer = new SimpleKafkaClient\Producer($conf);
```