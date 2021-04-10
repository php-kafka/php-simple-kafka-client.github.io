---
title: "abortTransaction"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function abortTransaction(int $timeoutMs): void {}
```
This function should also be used to recover from non-fatal abortable transaction errors.  
Any outstanding messages will be purged and fail with `RD_KAFKA_RESP_ERR__PURGE_INFLIGHT` or `RD_KAFKA_RESP_ERR__PURGE_QUEUE`.
## Example
```php
$conf = SimpleKafkaClient\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$producer = new SimpleKafkaClient\Producer($conf);
try {
    $producer->initTransactions(10000);
} catch (SimpleKafkaClient\KafkaErrorException $e) {
    if ($e->$transactionRequiresAbort()) {
        $producer->abortTransaction(10000);
    }
}
```