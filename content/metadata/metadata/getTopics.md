---
title: "getTopics"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function getTopics(): Metadata\Collection {}
```
Get metadata of all topics (or a single topic if one was provided)
Will return a `Metadata\Collection` of `Metadata\Topic`
## Example
```php
$conf = new Kafka\Configuration();
$conf->set('auto.offset.reset', 'earliest');
$producer = new Kafka\Producer($conf);
$metadata = $producer->getMetadata(false, 10000);
echo 'Info about topics' . PHP_EOL;
$topics = $metadata->getTopics();
while ($topics->valid()) {
    echo sprintf('Topic name: %s', $topics->current()->getTopic()) . PHP_EOL;

    $topics->next();
}
```