---
title: "setPartition"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function setPartition(int $partition): TopicPartition {}
```
Set partition of topic partition
## Example
```php
$topicPartition = new Kafka\TopicPartiton('test-topic', 0);
$topicPartition->setPartition(1);
```