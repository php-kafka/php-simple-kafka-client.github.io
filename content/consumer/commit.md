---
title: "commit"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
```php
/**
 * @throws SimpleKafkaClient\Exception
 */
public function commit($messageOrOffsets): void {}
```
Commit offsets synchronously, block until offsets are  
committed or the commit fails and an exception is thrown.
## Parameter details
- If `null` is passed, latest offsets for the current assignment will be committed
- Ìf a `SimpleKafkaClient\Message` is passed, commit offset for a single topic+partition based on the message
- If an array of `SimpleKafkaClient\TopicPartition` is passed, commit offsets for the provided list of partitions

## Example
```php
$conf = SimpleKafkaClient\Configuration();
$conf->set('metadata.broker.list', 'kafka:9092');
$consumer = new SimpleKafkaClient\Consumer($conf);
$message = $consumer->consume(20000);

if (RD_KAFKA_RESP_ERR_NO_ERROR !== $message->err) {
    echo 'An error occured:' . rd_kafka_err2str($message->err) . PHP_EOL;
    return;
}

$consumer->commit($message);
```