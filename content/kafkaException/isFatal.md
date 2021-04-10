---
title: "isFatal"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function isFatal(): bool {}
```
Check if it is a fatal exception
## Example
```php
$conf = SimpleKafkaClient\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$producer = new SimpleKafkaClient\Producer($conf);
try {
    $producer->initTransactions(10000);
} catch (SimpleKafkaClient\KafkaErrorException $e) {
    if ($e->isFatal()) {
        // non-recoverable error
    }
}
```