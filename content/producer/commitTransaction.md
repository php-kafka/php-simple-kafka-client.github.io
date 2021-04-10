---
title: "commitTransaction"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function commitTransaction(int $timeoutMs): void {}
```
Commit the current transaction (as started with `SimpleKafkaClient\Producer::beginTransaction()`).  
Any outstanding messages will be flushed (delivered) before actually committing the transaction.  
If any of the outstanding messages fail permanently the current transaction will enter the  
abortable error state and this function will return an abortable error, in this case the  
application must call `SimpleKafkaClient\Producer::abortTransaction()` before attempting a new  
transaction with `SimpleKafkaClient\Producer::beginTransaction()`.
## Example
```php
$conf = SimpleKafkaClient\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$producer = new SimpleKafkaClient\Producer($conf);
$producer->initTransactions(10000);
$producer->beginTransaction();
// produce some messsages
$producer->commitTransaction(10000);
```