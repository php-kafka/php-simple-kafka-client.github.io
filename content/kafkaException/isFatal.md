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
$conf = Kafka\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$producer = new Kafka\Producer($conf);
try {
    $producer->initTransactions(10000);
} catch (Kafka\KafkaErrorException $e) {
    if ($e->isFatal()) {
        // non-recoverable error
    }
}
```