---
title: "getOrigBrokerName"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function getOrigBrokerName(): string {}
```
Get broker name originating this metadata
## Example
```php
$conf = new SimpleKafkaClient\Configuration();
$conf->set('auto.offset.reset', 'earliest');
$producer = new SimpleKafkaClient\Producer($conf);
$metadata = $producer->getMetadata(false, 10000);
echo sprintf('Broker id: %d', $metadata->getOrigBrokerName()) . PHP_EOL;
```