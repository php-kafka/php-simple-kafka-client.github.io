---
title: "getId"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function getId(): int {}
```
Topic partition id reported by broker
## Example
```php
$conf = new Kafka\Configuration();
$conf->set('auto.offset.reset', 'earliest');
$producer = new Kafka\Producer($conf);
$metadata = $producer->getMetadata(false, 10000);
echo sprintf(
    'Topic partition error: %d',
    $metadata->getTopics()->current()->getPartitions()->current()->getId()
) . PHP_EOL;
```