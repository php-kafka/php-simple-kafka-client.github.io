---
title: "purge"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function purge(int $purgeFlags): int {}
```
Purges messages handled by the producer.  
The application will need to call `poll()` or `flush()` afterwards  
to serve the delivery report callbacks of the purged messages.  
Messages purged from internal queues fail with the delivery report error code  
set to `RD_KAFKA_RESP_ERR__PURGE_QUEUE`, while purged messages that are in-flight  
to or from the broker will fail with the error code set to `RD_KAFKA_RESP_ERR__PURGE_INFLIGHT`.
## Purge flags
- `RD_KAFKA_PURGE_F_QUEUE` purge internal queue
- `RD_KAFKA_PURGE_F_INFLIGHT` purge messages in-flight to or from the broker
- `RD_KAFKA_PURGE_F_NON_BLOCKING` make the call non-blocking
## Example
```php
$conf = SimpleKafkaClient\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$producer = new SimpleKafkaClient\Producer($conf);
// produce some messsages
$producer->purge(RD_KAFKA_PURGE_F_QUEUE);
```