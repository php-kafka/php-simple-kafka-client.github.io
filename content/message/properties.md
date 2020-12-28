---
title: "Properties"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Description
The message object's data can be accessed by it's public properties
- `err` the error code (or in case of success `RD_KAFKA_RESP_ERR_NO_ERROR`)
- `topic_name` topic name of message
- `partition` partition number of message
- `payload` payload of the message
- `len` length of the payload
- `key` key of the message
- `offset` offset of the message
- `headers` headers of the message (or `null`)