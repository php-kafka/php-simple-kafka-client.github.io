---
title: "getHost"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function getHost(): string {}
```
Get host name of metadata broker
## Example
```php
$conf = new Kafka\Configuration();
$conf->set('auto.offset.reset', 'earliest');
$producer = new Kafka\Producer($conf);
$metadata = $producer->getMetadata(false, 10000);
echo sprintf('Broker host: %s', $metadata->getBrokers()->current()->getHost()) . PHP_EOL;
```