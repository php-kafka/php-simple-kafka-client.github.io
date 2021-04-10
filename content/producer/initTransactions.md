---
title: "initTransactions"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function initTransactions(int $timeoutMs): void  {}
```
Initialize transactions for the producer instance.  
This function ensures any transactions initiated by previous instances of  
the producer with the same `transactional.id` are completed.  
If the previous instance failed with a transaction in progress the previous  
transaction will be aborted. This function needs to be called before any other  
transactional or produce functions are called when the `transactional.id` is configured.
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