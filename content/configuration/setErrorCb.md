---
title: "setErrorCb"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function setErrorCb(callable $callback): void {}
```
Gets triggered for every error that occurs in `librdkafka`, keep in mind  
that non-critical errors will be retried by `libdrkafka`

## Example
```php
$conf = new SimpleKafkaClient\Configuration();
$conf->setErrorCb(
    function (SimpleKafkaClient\Kafka $kafka, $errorCode, $reason) {
        //do something
    }
);
```