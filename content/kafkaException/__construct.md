---
title: "__construct"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
public function __construct(
    string $message,
    int $code,
    string $error_string,
    bool $isFatal,
    bool $isRetriable,
    bool $transactionRequiresAbort
) {}
```
Create new `KafkaErrorException`, this can be helpful for transaction tests
## Example
```php
throw new Kafka\KafkaErrorException(
    'Some error message',
    88,
    'This is a detailed error string',
    false,
    true,
    false
);
```