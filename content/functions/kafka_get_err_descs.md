---
title: "kafka_get_err_descs"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
```php
function kafka_get_err_descs(): array {}
```
Returns a full list of error codes and their description, see example:
```php
[
    [
        "code" => 88,
        "name" => "UNSTABLE_OFFSET_COMMIT",
        "desc" => "Broker: There are unstable offsets that need to be cleared"
    ],
    ...
]
```
