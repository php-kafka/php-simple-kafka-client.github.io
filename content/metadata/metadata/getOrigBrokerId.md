---
title: "getOrigBrokerId"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function getOrigBrokerId(): int {}
```
Get broker id originating this metadata
## Example
```php
$conf = new Kafka\Configuration();
$conf->set('auto.offset.reset', 'earliest');
$producer = new Kafka\Producer($conf);
$metadata = $producer->getMetadata(false, 10000);
echo sprintf('Broker id: %d', $metadata->getOrigBrokerId()) . PHP_EOL;
```