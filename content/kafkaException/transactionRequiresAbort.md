---
title: "transactionRequiresAbort"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function transactionRequiresAbort(): bool {}
```
Check if error needs the transaction to be aborted
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