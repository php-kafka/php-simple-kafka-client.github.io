---
title: "beginTransaction"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function beginTransaction(): void {}
```
`Kafka\Producer::initTransactions()` must have been called successfully (once)  
before this function is called. Any messages produced, offsets sent, etc,  
after the successful return of this function will be part of the transaction  
and committed or aborted automatically.  
Finish the transaction by calling `Kafka\Producer::commitTransaction()`  
or abort the transaction by calling `Kafka\Producer::abortTransaction()`
```php
$conf = Kafka\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$producer = new Kafka\Producer($conf);
$producer->initTransactions(10000);
$producer->beginTransaction();
// produce some messsages
$producer->commitTransaction(10000);
```