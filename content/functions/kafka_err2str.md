---
title: "kafka_err2str"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
function kafka_err2str(int $errorCode): string {}
```
Returns the error message of an error code
## Example
```shell
php> echo kafka_err2str(88);
Broker: There are unstable offsets that need to be cleared
```
