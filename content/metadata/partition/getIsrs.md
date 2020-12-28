---
title: "getIsrs"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function getIsrs(): Collection {}
```
Topic partition in-sync replicas reported by broker
## Example
```php
$conf = new Kafka\Configuration();
$conf->set('auto.offset.reset', 'earliest');
$producer = new Kafka\Producer($conf);
$metadata = $producer->getMetadata(false, 10000);
$isrs = $metadata->getTopics()->current()->getPartitions()->current()->getIsrs();
while ($isrs->valid()) {
    echo sprintf('Insync Replicas id: %d', $isrs->current()) . PHP_EOL;
    $isrs->next();
}
```