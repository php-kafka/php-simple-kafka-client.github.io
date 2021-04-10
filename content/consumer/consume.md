---
title: "consume"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function consume(int $timeoutMs): Message {}
```
Consume message(s) (will also get error events and triggers callbacks)  
Registered callbacks will be automaically called `rebalanceCallback`, `logCallback`, etc.  
On error `$message->err` will not be `RD_KAFKA_ERR_NO_ERROR` but contain the acutal error code.
## Example
```php
$conf = SimpleKafkaClient\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$consumer = new SimpleKafkaClient\Consumer($conf);
$message = $consumer->consume(20000);
```
{{< hint info >}}
An application should call consume() at regular intervals, even if no messages  
are expected, to serve any queued callbacks waiting to be called.
{{< /hint >}}