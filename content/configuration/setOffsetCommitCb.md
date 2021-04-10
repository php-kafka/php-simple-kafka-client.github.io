---
title: "setOffsetCommitCb"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function setOffsetCommitCb(callable $callback): void {}
```
Set offset commit callback for use with consumer groups.  
The results of automatic or manual offset commits will be scheduled  
for this callback.  If no partitions had valid offsets to commit  
this callback will be called with `err == RD_KAFKA_RESP_ERR__NO_OFFSET`  
which is not to be considered an error.
## Example
```php
$conf = new SimpleKafkaClient\Configuration();
$conf->setOffsetCommitCb(
    function (SimpleKafkaClient\Kafka $kafka, int $errorCode, array $topicPartition) {
        if (RD_KAFKA_RESP_ERR_NO_ERROR === $errorCode) {
            echo 'Commit was successful';
        } else {
            echo 'Commit failed';
        }
    }
);
```