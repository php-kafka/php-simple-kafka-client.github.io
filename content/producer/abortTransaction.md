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
$conf = Kafka\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$producer = new Kafka\Producer($conf);
try {
    $producer->initTransactions(10000);
} catch (Kafka\KafkaErrorException $e) {
    if ($e->$transactionRequiresAbort()) {
        $producer->abortTransaction(10000);
    }
}
```