---
title: "getBrokers"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function getBrokers(): Metadata\Collection {}
```
Get metadata of all brokers
Will return a `Metadata\Collection` of `Metadata\Broker`
## Example
```php
$conf = new Kafka\Configuration();
$conf->set('auto.offset.reset', 'earliest');
$producer = new Kafka\Producer($conf);
$metadata = $producer->getMetadata(false, 10000);
echo $metadata->getBrokers()->current()->getHost() . PHP_EOL;
echo $metadata->getBrokers()->current()->getPort() . PHP_EOL;
```