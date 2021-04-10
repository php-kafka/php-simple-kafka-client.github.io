---
title: "setRebalanceCb"
date: 2020-12-27T22:09:37+01:00
draft: false
geekdocCollapseSection: true
---
## Description
```php
public function setRebalanceCb(callable $callback): void {}
```
Set a rebalance callback for use with coordinated consumer group balancing.  
The `$errorCode` is set to either `RD_KAFKA_RESP_ERR__ASSIGN_PARTITIONS`  
or `RD_KAFKA_RESP_ERR__REVOKE_PARTITIONS` and 'partitions' contains  
the full partition set that was either assigned or revoked.  
  
Registering a rebalance callback turns off the automatic partition  
assignment/revocation and instead delegates that responsibility  
to the application's callback.

## Example
```php
$conf = new SimpleKafkaClient\Configuration();
$conf->setRebalanceCb(
    function (SimpleKafkaClient\Consumer $kafka, int $errorCode, array $partitions = null) {
        case RD_KAFKA_RESP_ERR__ASSIGN_PARTITIONS:
            $kafka->assign($partitions);
            break;

         case RD_KAFKA_RESP_ERR__REVOKE_PARTITIONS:
             if ($manual_commits) {
                 // Optional explicit manual commit
                 $kafka->commit($partitions);
             }
             //revoke partitions
             $kafka->assign(NULL);
             break;

         default:
            // handle arbitrary rebalancing failure
            ...
            // synchronize state
            $kafka->assign(NULL);
            break;
    }
);
```