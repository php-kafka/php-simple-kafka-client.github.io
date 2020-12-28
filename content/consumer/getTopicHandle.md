---
title: "getTopicHandle"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function getTopicHandle(string $topic): ConsumerTopic {}
```
Get a topic handle for a given topic name. A topic handle is needed  
for example to query metadata from the broker
## Example
```php
$conf = Kafka\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$consumer = new Kafka\Consumer($conf);
$topicHandle = $consumer->getTopicHandle('test-topic');

// use the topic handle for further calls, e.g. to query metadata
$singleTopicMetadata = $consumer->metadata(true, $topicHandle, 10000);
```