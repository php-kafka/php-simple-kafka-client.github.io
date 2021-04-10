---
title: "getPartition"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function getPartition(): int {}
```
Get partition of topic partition
## Example
```php
$topicPartition = new SimpleKafkaClient\TopicPartiton('test-topic', 0, 100);
echo sprintf('TopicPartition partition %d', $topicPartition->getPartition()) . PHP_EOL;
```