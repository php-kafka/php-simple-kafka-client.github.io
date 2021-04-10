---
title: "getPartitions"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function getPartitions(): Collection {}
```
Topic partitions reported by broker
## Example
```php
$conf = new SimpleKafkaClient\Configuration();
$conf->set('auto.offset.reset', 'earliest');
$producer = new SimpleKafkaClient\Producer($conf);
$metadata = $producer->getMetadata(false, 10000);
$topicPartitionsMetadata = $metadata->getTopics()->current()->getPartitions();
```