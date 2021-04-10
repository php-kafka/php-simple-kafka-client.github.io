---
title: "flush"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function flush(int $timeoutMs): int {}
```

Wait until all outstanding produce requests, et.al, are completed.  
This should typically be done prior to destroying a producer instance to make sure  
all queued and in-flight produce requests are completed before terminating.  
This function will call poll() and thus trigger callbacks.
## Example
```php
$conf = SimpleKafkaClient\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$producer = new SimpleKafkaClient\Producer($conf);
// produce some messsages
$producer->flush(10000);
```