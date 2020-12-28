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
$conf = Kafka\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$producer = new Kafka\Producer($conf);
$topicHandle = $producer->getTopicHandle('test-topic');
$singleTopicMetadata = $producer->metadata(true, $topicHandle, 10000);
```