---
title: "getTopicName"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function getTopicName(): string {}
```
Get topic name of topic partition
## Example
```php
$topicPartition = new Kafka\TopicPartiton('test-topic', 0, 100);
echo sprintf('Topic partition name %s', $topicPartition->getTopicName()) . PHP_EOL;
```