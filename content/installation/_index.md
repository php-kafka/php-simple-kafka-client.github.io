---
title: "Installation"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Installation with PECL
```
pecl install simple_kafka_client
```

### Manual installation
```bash
git clone https://github.com/php-kafka/php-simple-kafka-client.git
cd php-simple-kafka-client
phpize && ./configure && make -j5 all && make install
```
In your `php/conf.d` folder add a `simple_kafka_client.ini` with the following:
```ini
extension=simple_kafka_client.so
```
