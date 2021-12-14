---
title: "About"
date: 2020-12-27T22:09:37+01:00
draft: false
---

[![Supported librdkafka versions: >= 1.6.0](https://img.shields.io/badge/librdkafka-%3E%3D%201.6.0-blue.svg)](https://github.com/edenhill/librdkafka/releases)
[![Supported Kafka versions: >= 0.9](https://img.shields.io/badge/kafka-%3E%3D%200.9-blue.svg)](https://github.com/edenhill/librdkafka/blob/master/INTRODUCTION.md#broker-version-compatibility)
![Supported PHP versions: 7.4 .. 8.x](https://img.shields.io/badge/php-7.4%20..%208.x-blue.svg)
[![License: BSD-3](https://img.shields.io/badge/License-BSD--3-green.svg)](https://github.com/php-kafka/php-simple-kafka-client/blob/main/LICENSE)
[![Join the chat at https://gitter.im/php-kafka/php-simple-kafka-client](https://badges.gitter.im/php-kafka/php-simple-kafka-client.svg)](https://gitter.im/php-kafka/php-simple-kafka-client?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

This extension provides ways to interact with Apache Kafka.  
It also supports any system that is Kafka API compatible like Redpanda.  
You can find some examples for producer and consumer [here](https://github.com/php-kafka/php-kafka-examples/tree/main/src/ext-php-simple-kafka-client)  
This extension uses [librdkafka](https://github.com/edenhill/librdkafka) for binding and was inspired by [php-rdkafka](https://github.com/arnaud-lb/php-rdkafka).  
**Notice:** php-rdkafka conflicts with this extension, please uninstall it first if you want to use simple-kafka-client.
