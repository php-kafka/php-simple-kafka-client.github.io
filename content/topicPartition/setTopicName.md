---
title: "setTopicName"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function setTopicName(string $topicName): TopicPartition {}
```
Set topic name of topic partition
## Example
```php
$topicPartition = new SimpleKafkaClient\TopicPartiton('test-topic', 0);
$topicPartition->setTopicName('another-test-topic');
```