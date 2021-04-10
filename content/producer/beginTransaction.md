---
title: "beginTransaction"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function beginTransaction(): void {}
```
`SimpleKafkaClient\Producer::initTransactions()` must have been called successfully (once)  
before this function is called. Any messages produced, offsets sent, etc,  
after the successful return of this function will be part of the transaction  
and committed or aborted automatically.  
Finish the transaction by calling `SimpleKafkaClient\Producer::commitTransaction()`  
or abort the transaction by calling `SimpleKafkaClient\Producer::abortTransaction()`
```php
$conf = SimpleKafkaClient\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$producer = new SimpleKafkaClient\Producer($conf);
$producer->initTransactions(10000);
$producer->beginTransaction();
// produce some messsages
$producer->commitTransaction(10000);
```