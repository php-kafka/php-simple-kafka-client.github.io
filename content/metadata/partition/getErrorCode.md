---
title: "getErrorCode"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function getErrorCode(): int {}
```
Topic partition error code reported by broker
## Example
```php
$conf = new Kafka\Configuration();
$conf->set('auto.offset.reset', 'earliest');
$producer = new Kafka\Producer($conf);
$metadata = $producer->getMetadata(false, 10000);
echo sprintf(
    'Topic partition error code: %d',
    $metadata->getTopics()->current()->getPartitions()->current()->getErrorCode()
) . PHP_EOL;
```