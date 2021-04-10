---
title: "setOffset"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function setOffset(int $offset): TopicPartition {}
```
Set offset of topic partition
## Example
```php
$topicPartition = new SimpleKafkaClient\TopicPartiton('test-topic', 0);
$topicPartition->setOffset(100);
```