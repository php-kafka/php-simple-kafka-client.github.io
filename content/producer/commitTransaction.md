---
title: "commitTransaction"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function commitTransaction(int $timeoutMs): void {}
```
Commit the current transaction (as started with `Kafka\Producer::beginTransaction()`).  
Any outstanding messages will be flushed (delivered) before actually committing the transaction.  
If any of the outstanding messages fail permanently the current transaction will enter the  
abortable error state and this function will return an abortable error, in this case the  
application must call `Kafka\Producer::abortTransaction()` before attempting a new  
transaction with `Kafka\Producer::beginTransaction()`.
## Example
```php
$conf = Kafka\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$producer = new Kafka\Producer($conf);
$producer->initTransactions(10000);
$producer->beginTransaction();
// produce some messsages
$producer->commitTransaction(10000);
```