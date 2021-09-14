---
title: "Installation"
date: 2020-12-27T22:09:37+01:00
draft: false
---
## Installation with PECL
```
pecl install simple_kafka_client
```

## Alpine Linux
For PHP7:
```shell
apk add php7-pecl-simple-kafka-client --update-cache --repository http://dl-3.alpinelinux.org/alpine/edge/testing/
```
For PHP8:
```shell
apk add php8-pecl-simple-kafka-client --update-cache --repository http://dl-3.alpinelinux.org/alpine/edge/testing/
```

## Windows
You can find the DLLs on PECL as well. If you experience an error similar to this:
```
The procedure entry point rd_kafka_abort_transaction could not be located in the dynamic library librdkafka.dll
```
1. Most likely you have an outdated version of `librdkaka` in use. Note that `librdkaka.dll` needs to be in the `PATH`.  
putting it in the ext/ directory does not make it available. Be sure to overwrite any previous versions.
2. This can also happen if an old version of `librdkafka.dll` is packaged during the PECL build.  
You can download newer versions of the `librdkafka.dll` [here](https://www.nuget.org/packages/librdkafka.redist)  
You can find the DLLs in the `runtimes` sub-folder.

## Manual installation
```bash
git clone https://github.com/php-kafka/php-simple-kafka-client.git
cd php-simple-kafka-client
phpize && ./configure && make -j5 all && make install
```
In your `php/conf.d` folder add a `simple_kafka_client.ini` with the following:
```ini
extension=simple_kafka_client.so
```
