---
title: "kafka_err2name"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
function kafka_err2name(int $errorCode): string {}
```
Returns the name of the error
## Example
```shell
php> echo kafka_err2name(88);
UNSTABLE_OFFSET_COMMIT
```
