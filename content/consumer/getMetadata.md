---
title: "getMetadata"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
function getMetadata(bool $allTopics, int $timeoutMs, ConsumerTopic $topic = null): Metadata {}
```
Get metadata for all topics or a single topic
## Example
```php
$conf = SimpleKafkaClient\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$consumer = new SimpleKafkaClient\Consumer($conf);
$topicHandle = $consumer->getTopicHandle('test-topic');
$singleTopicMetadata = $consumer->metadata(true, $topicHandle, 10000);
```