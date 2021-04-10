---
title: "set"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function set(string $name, string $value): void {}
```
Set a configuration value

## Example
```php
$conf = new SimpleKafkaClient\Configuration();
$conf->set('auto.offset.reset', 'earliest');
```
