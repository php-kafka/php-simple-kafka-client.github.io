---
title: "setStatsCb"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function setStatsCb(callable $callback): void {}
```
Set a statistics callback  
The statistics callback is triggered every `statistics.interval.ms` (needs to be configured separately).
## Example
```php
$conf = new SimpleKafkaClient\Configuration();
$conf->setStatsCb(
    function (SimpleKafkaClient\Kafka $kafka, string $json, int $jsonLength) {
        //do something
    }
);
```