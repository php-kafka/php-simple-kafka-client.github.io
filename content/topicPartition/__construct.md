---
title: "__construct"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function __construct(string $topicName, int $partition, int $offset = 0) {}
```
Create new topic partition instance
## Example
```php
$topicPartition = new Kafka\TopicPartiton('test-topic', 0);
```