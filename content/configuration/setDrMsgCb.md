---
title: "setDrMsgCb"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function setDrMsgCb(callable $callback): void {}
```
Set a message delivery report callback  
This callback is called exactly once per message, indicating if  
the message was succesfully delivered or permanently failed delivery

## Example
```php
$conf = new Kafka\Configuration();
$conf->setDrMsgCb(
    function (Producer $kafka, Message $message) {
        if (RD_KAFKA_RESP_ERR_NO_ERROR !== $message->err) {
            $errorStr = rd_kafka_err2str($message->err);
    
            echo sprintf('Message FAILED (%s, %s) to send with payload => %s', $message->err, $errorStr, $message->payload) . PHP_EOL;
        } else {
            // message successfully delivered
            echo sprintf('Message sent SUCCESSFULLY with payload => %s', $message->payload) . PHP_EOL;
        }
    }
);
```