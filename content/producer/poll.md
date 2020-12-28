---
title: "poll"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function poll(int $timeoutMs): int {}
```
Polls for events, provided callbacks will be called accordingly
## Example
```php
$conf = Kafka\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$producer = new Kafka\Producer($conf);
// produce some messsages
$producer->poll(0);
```
{{< hint info >}}
The producer needs to call `poll` at regular intervals to serve any queued callbacks  
waiting to be called, otherwise the internal queue fill up and block the producer.
{{< /hint >}}