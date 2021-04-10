---
title: "getName"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function getName(): string {}
```
Get topic name
## Example
```php
$conf = new SimpleKafkaClient\Configuration();
$conf->set('auto.offset.reset', 'earliest');
$consumer = new SimpleKafkaClient\Consumer($conf);
$consumerTopic = $consumer->getTopicHandle('test-topic');
echo sprintf('Topic name: %s', $consumerTopic->getName()) . PHP_EOL;
```