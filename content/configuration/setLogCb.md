---
title: "setLogCb"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function setLogCb(callable $callback): void {}
```
Set a log callback  
You will get events according to the `log_level` setting
## Example
```php
$conf = new Kafka\Configuration();
$conf->setLogCb(
    function (Kafka\Kafka $kafka, int $level, string $facility, string $message) {
        //do something
    }
);
```